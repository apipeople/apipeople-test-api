# APIPeople Test API
API Template act as foundation for developers to start building APIs. They need not worry about adding dependencies and configure auto discovery as all is handled by the template. The template utilizes 2 Mule Extensions as follows,
1. JSON Logger: This is used for Logging in the API and this custom plugin published to APIPeople exchange.
2. Error Handler Plugin: This is a common error handler that is fully customizable and is used by the template to handle errors. In case of an error the On Error Propgate is used which sends the information to the error handler which then handles the error, maps to the error object and prints it. This plugin also published to APIPeople exchange.

## Template Features

1. Logging - Uses the JSON Logger to take care of logging
2. Error Handling - Uses the Error Handler Plugin to conduct error handling
3. API Autodiscovery - Is preconfigured with API Autodiscovery and only the API ID needs to be provided.
4. Preconfigured APIKIT Router - Uses the APIKit router which has been configured with the necessary information
5. End to End Transaction Handling

## Deploying to Exchange
To deploy to Exchange, use `mvn clean deploy`

Please ensure that your settings.xml has been configured with the APIPeople Exchange credentials so that the publish can succeed.

## Local Install
For local install, Issue `mvn clean install`

## Usage

Import the API Template from Exchange and into Studio and start building the business logic for your API

1. Rename Mule Project from *apipeople-api-template* to `<YOUR_API_NAME>`
2. Import RAML spec from Design Center and generate the flows.
3. To run the application locally you need to pass the following JVM arguments: -Denv=dev -Dsecret.key=xxxx 
4. Template app configured to support 3 types of deployments **CloudHub 2.0**, **CloudHub** and **RTF**.
   While deploying the application pass **target** value as **CH2.0**, **CH** or **RTF** to activate the required profile.