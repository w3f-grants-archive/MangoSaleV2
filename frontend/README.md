# Setup mangosale Front-end

## Install `Polkadot JS Extension`

Please install `Polkadot JS Extension` before you start. You can get it from here https://polkadot.js.org/extension/

### Get source code

Please get the code from https://github.com/Mangoboxlabs/MangoSale.git

```
git clone https://github.com/Mangoboxlabs/MangoSale.git
```

## Project setup

```
cd frontend
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

 Open http://localhost:8080 to view it in your browser. 

### Compiles and minifies for production

```
npm run build
```

### docker

```
npm run build
npm run docker:build
docker run -p8080:80 mangosale/ui1:v1
```



### cypress e2e Test

```
npx cypress open
```

* Before testing, you need to import the wallet plug-in into the test browser and create an account into gas

  

*  Wallet plugin address: https://github.com/Mangoboxlabs/MangoSale/tree/main/frontend/master-build.zip

#### 1) Download the plugin given 

#### 2) Open e2e Test Page

![3](./img/4.jpg)

#### 3) Install the polkadot.js in the cypress browser ：

##### 1. In More tools  Open Extentions

![1](./img/1.png)

##### 2.Open Developer mode

![2](./img/2.jpg)

##### 3.Click Load unpacked to add download  polkadot.js   Extention

![3](./img/3.jpg)



#### 4)  Start testing 

#####  Test sequence :  

`createToken.cy => createLaunchpad.cy => purchaseToken.cy`

![3](./img/6.jpg)

## Way 2: Local Node Test

### Config front-end

Please find the correct address for `src/api/apiMap.js`, and update the correct address in `src/api/apiMap.js`. And replace `src/api/httpConfig.js connectPath` to your connect path.

it should be `ws://127.0.0.1:9900` by default.
#### Copy ABI
When the contract content changes, it is necessary to copy the contract abi to ``src/abi``.
The contract ABI is under the contract directory``target/ink/metadata.json``
#### Ipfs Config

`src/utils/ipfsApi.js`  `pinataConfig`

get APIKey、APISecret and JWT from https://app.pinata.cloud/

### gas

1. Open https://polkadot.js.org/apps/
2. Add localhost path(like `ws://127.0.0.1:9900` ) to local node
3. Use an account(like Alice) to wire money into a `Polkadot JS Extension` wallet



## Way 2: Use the online version front-end test deployed contract

### entrance:

[https://sale.mangobox.xyz/](https://sale.mangobox.xyz/)

### gas

1. Open https://polkadot.js.org/apps
2. Add wss://rpc.mangobox.xyz/ to local node
3. Use an account(like Alice) to wire money into a `Polkadot JS Extension` wallet

##### Then

You can use `https://sale.mangobox.xyz/` to create token/multisign wallet. Test Protocol Management.

