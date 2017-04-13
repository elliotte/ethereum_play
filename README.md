# ethereum-auth-demo
Demo of signing into a backend website from Web3 using JSON Web Tokens.

## Project
Cloned from https://github.com/vanbexlabs/ethereum-auth-demo
Small tweak to script made

## Installation
    npm install
    browserify frontend.js > public/bundle.js
    npm start

## How to use
1. Install MetaMask in Chrome / Chromium and create an Ethereum account.
2. Browse to localhost:3000. You should see information about the Ethereum network and your account address.
3. Click "Sign in". You will be prompted in MetaMask to sign the message "Sign into demo app."
4. Click "Who am I" to check the backend knows your account address.

## How does it work
* The Web3 environment (MetaMask / Mist) is requested to sign a message using the account's private key.
* The account address and the signed message are POSTed to the backend.
* The backend verifies that the signature is correct and generates a signed Json Web Token (JWT) proving that the holder is in control of the address.
* The JWT is sent back to the web browser as a HttpOnly (not accessible from frontend JS) session cookie.
* When "Who am I" is clicked, the JWT cookie is checked and the address of account is returned to the browser.

## Todo
Include a CSRF token to prevent cross-site request forgery. See https://stormpath.com/blog/where-to-store-your-jwts-cookies-vs-html5-web-storage
