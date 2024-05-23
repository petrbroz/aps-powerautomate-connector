# aps-powerautomate-connector

Experimental Microsoft Power Automate connector for Autodesk Platform Services.

## Usage

- Go to https://make.powerautomate.com
- Go to _Custom connectors_
  - Note: if you can't see this option in the left sidebar, click the _... More_, then _Discover all_, and select _Custom connectors_ from there
- In the top-right corner, expand the _New custom connector_ menu, and select _Import an OpenAPI from URL_
- Name your connector, and use the following URL: https://raw.githubusercontent.com/petrbroz/aps-powerautomate-connector/master/build/aps-powerautomate-connector.yaml

## Development

- Clone this repository
- Install development dependencies: `yarn install`
- Update the OpenAPI specs as needed
- Run `yarn run bundle` to bundle all the specs into a single file (_build/aps-powerautomate-connector.yaml_)