# Deposits MX Add bank Setup

## _How to implement add bank via MX widget on web/mobile via the API_


baseUrl for the Deposits API in sandbox
```sh
https://api.deposits.dev
```
baseUrl for the Deposits API in production
```sh
https://api.ondeposits.com
```

## _Mobile_

When one needs to add a bank via MX you have to call the deposits API in the format below and ensure you pass the right public_key, entity_type and the right entity_id and the URL has to be opened in a webview.

```sh
{baseUrl}/api/v2/mx-popup/{type}/{public_key}/{entity_id}
```

```sh
{type} is the type of entity and is either user or business
```

```sh
{public_key} is the public_key of the program gotten from our console
```

```sh
{entity_id} is the id of the entity and is either user_id or business_id
```

when the bank account has been added and the verification process complete on the backend we open a URL depending on the tenant and the environment.
Below is a deeplink for Money by Deposits App

Deeplink for the Money by Deposits App in sandbox
```sh
moneyondepositsstaging://addbank?token=123
```
Deeplink for the Money by Deposits App in production
```sh
moneyondeposits://addbank?token=123
```


## _Web_

When one needs to add a bank via MX you have to call the deposits API in the format below and ensure you pass the right public_key and the right user_id and the URL has to be opened in an iframe.

```sh
{baseUrl}/api/v2/mx-popup/{type}/{public_key}/{entity_id}
```

```sh
{type} is the type of entity and is either user or business
```

```sh
{public_key} is the public_key of the program gotten from our console
```

```sh
{entity_id} is the id of the entity and is either user_id or business_id
```

when the bank account has been added and the verification process complete on the backend an event 'memberConnected' is sent to the parent window via Javascript and once this event is received, the iframe can then be closed or removed from the DOM.
Below is a sample code we have you can use on any Javascript project
```sh
  let baseUrl = "depositsBaseUrl" //sandbox or prod
  let type = "myUserID"
  let apiKey = "myApiKey"
  let entityId = "myUserID"

  let container = document.querySelector('#target'); // ensure you have a div with this id
  const iframe = document.createElement('iframe');
  iframe.style.height = '100vh'
  iframe.style.width = '100vw'
  iframe.style.top = '0'
  iframe.style.position = 'fixed'
  iframe.src = baseUrl+'/api/v2/mx-popup'+'/'+type+'/'+apiKey+'/'+entityId
  container.appendChild(iframe);

  window.addEventListener(
    'message',
    function(e) {
        // check if the event is from deposits either sandbox/prod
      if(e.origin.search("deposits.") > -1){
        // check if this is the right event to trigger the close
        if(e.data == 'memberConnected'){
          iframe.remove()
          // refresh your list of account or close the frame or refresh the page
        }
      }
    },
    false
  );
```

you can use the below example that connects opens the iframe through a function trigered by clicking on the button, the logic is in Laravel php and vanilla JS
```sh

    <button id="mxButton" onclick="openIframe('{{ $baseUrl }}', '{{ $type }}', '{{ $apiKey }}', '{{ $entityId }}')" class="ui-button my w-100 mt-2 semantic__primary mt-5 size__huge" type="submit">
                    <span class="ui-button__button-text"> Bank Login Via MX </span>
    </button>

  
    <script type="text/javascript">
        function openIframe(baseUrl, type, apiKey, entityId){

            let frameUrl = baseUrl+'/api/v2/mx-popup'+'/'+type+'/'+apiKey+'/'+entityId
            
            document.getElementById('theiframe').setAttribute('src', frameUrl);
            document.getElementById('theiframe').style.width = "100vw";
            document.getElementById('theiframe').style.height = "100vh";
            document.getElementById('theiframe').style.position = "fixed";
            document.getElementById('theiframe').style.top = "0";
            document.getElementById('theiframe').style.left = "0";
            document.getElementById('theiframe').style.right = "0";
            document.getElementById('theiframe').style.bottom = "0";
            document.getElementById('theiframe').style.border = "none";
            document.getElementById('theiframe').style.display = "block";
        }
    </script>
```

