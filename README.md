# Overview

This project is an example that uses Angular generated package in Flotiq.

## Prerequisites

1. Node >= 10.9
2. Npm >= 5.5.1
3. Flotiq Account - you can create one [here](https://editor.flotiq.com)
4. Your own content type definition. For example purpose I have created a `todolist` (API Name: `todolist`, Label: `to-do-list`) content object definition which contains:
    * title : type string
    * date : type string
    * description : type string
    * status : type string
5. Angular generated package which can be downloaded from your Flotiq dashboard after you log in.

<b>IMPORTANT!</b> To be 100% sure what names of services and models package created for you, go to package directory and check `api` and `model` folders and look for correspinding names. 

If you want quick setup and use Content Type Definition used by me you have to create such one by using the same names as mentioned in point 4!

## Installation instructions
Remember you have to build your generated package before injecting it into application. Read package README for detailed instructions or follow these below:
### In downloaded package directory:
1. npm install
2. npm run build

This will generate a `dist` folder in your downloaded package directory, which will be used later.

### In application directory:
1. npm install
2. npm install (path to your generated package)/dist
3. In (path to your generrated package)/dist run `npm link`
4. In your project directory run `npm link flotiq`



In `environment.ts` and `environment.prod.ts` provide an FLOTIQ_API_KEY suitable to your needs (full, readOnly, restricted to specific Content Type Definition);

## Run

1. npm start (you could use `ng serve` also, but your installed Angular version might be incompatible)

## Generate application files for production mode that can be deployed to your server:

1. npm build --prod

## Available demo:

https://flotiq-example.firebaseapp.com/entries

## Free hosting option

1. [Firebase hosting](https://firebase.google.com/docs/hosting)

## Known problems

If you receive an error `Error: You need to import the HttpClientModule in your AppModule!` you have to add a following line in your `tsconfig.app.json` file 
in `compilerOptions` section:

`"paths": { "@angular/*": [ "./node_modules/@angular/*" ] }`