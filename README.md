# aps-powerautomate-connector

Experimental Microsoft Power Automate connector for Autodesk Platform Services.

## Usage

### Importing the Connector into Power Automate

- While on https://make.powerautomate.com, go to _Custom connectors_
  - Tip: if you can't see this option in the left sidebar, click _... More_, then _Discover all_, and select _Custom connectors_ from there
- In the top-right corner, expand the _New custom connector_ menu, and select _Import an OpenAPI from URL_
- Give your connector some name (you'll need this name later), and import the following URL: https://raw.githubusercontent.com/petrbroz/aps-powerautomate-connector/master/build/aps-powerautomate-connector.yaml
- Adjust the connector icon and color scheme if needed
- Go to the _2. Security_ section
- Set your application's client ID and secret
- Copy the _Token URL_ into _Refresh URL_
  - The refresh URL *is* specified in the OpenAPI spec but for some reason the Power Automate import ignores it...
- Finish the creation of your connector using the _Create connector_ button in the top-right corner
- While still on the _2. Security_ section, copy the _Redirect URL_ and add it to your application's callbacks on https://aps.autodesk.com/myapps

### Using the Connector in your Power Automate flow

- When adding a new action or trigger, open the _Runtime_ dropdown in the left sidebar, and check _Custom_
- Find the connector based on the name you specified during the OpenAPI import
- You will see a couple of actions and triggers that you can now start using in your flow:

| Type | Name | Description |
|------|------|-------------|
| trigger | _When a new version of a design is uploaded_ | Will be triggered whenever a new design is uploaded to a specific folder in ACC. |
| action | _List issue categories and types_ | Will return all possible issue subtypes (a subtype ID is a required input when creating new issues). |
| action | _Create new issue_ | Will create a new issue in your ACC project. |

## Development

- Clone this repository
- Install development dependencies: `yarn install`
- Update the OpenAPI specs as needed
- Run `yarn run bundle` to bundle all the specs into a single file (_build/aps-powerautomate-connector.yaml_)