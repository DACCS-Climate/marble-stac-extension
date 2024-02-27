# Marble Platform Extension Specification

- **Title:** Marble
- **Identifier:** <https://stac-extensions.github.io/marble/v1.0.0/schema.json>
- **Field Name Prefix:** marble
- **Scope:** Item, Collection
- **Extension [Maturity Classification](https://github.com/radiantearth/stac-spec/tree/master/extensions/README.md#extension-maturity):** Proposal
- **Owner**: @dchandan

This document explains the [Marble Platform](https://marbleclimate.com) specific extension to the 
[SpatioTemporal Asset Catalog](https://github.com/radiantearth/stac-spec) (STAC) specification. It adds fields 
that describe the location of data on the Marble Network/Platform.

- Examples:
  - [Item example](examples/item.json): Shows the basic usage of the extension in a STAC Item
- [JSON Schema](json-schema/schema.json)
- [Changelog](./CHANGELOG.md)

## Fields

The fields in the table below can be used in these parts of STAC documents:

- [ ] Catalogs
- [x] Collections
- [x] Item Properties (incl. Summaries in Collections)
- [ ] Assets (for both Collections and Items, incl. Item Asset Definitions in Collections)
- [ ] Links

| Field Name           | Type                      | Description                                  |
| -------------------- | ------------------------- | -------------------------------------------- |
| marble:host_node | string                    | **REQUIRED**. Name of the Marble node hosting the data |
| marble:is_local      | boolean | **REQUIRED**. Whether this data is local on the node being searched |

### Additional Field Information

#### marble:host_node

This is a controlled vocabulary and the values can be one of the node names currently available in the 
[Marble node registry](https://github.com/DACCS-Climate/Marble-node-registry).

#### marble:is_local

If `true`, it means that the data is locally available on the node where the search is being performed. If `false`, it means
the data is available on another federated node.

## Contributing

All contributions are subject to the
[STAC Specification Code of Conduct](https://github.com/radiantearth/stac-spec/blob/master/CODE_OF_CONDUCT.md).
For contributions, please follow the
[STAC specification contributing guide](https://github.com/radiantearth/stac-spec/blob/master/CONTRIBUTING.md) Instructions
for running tests are copied here for convenience.

### Running tests

The same checks that run as checks on PR's are part of the repository and can be run locally to verify that changes are valid. 
To run tests locally, you'll need `npm`, which is a standard part of any [node.js installation](https://nodejs.org/en/download/).

First you'll need to install everything with npm once. Just navigate to the root of this repository and on 
your command line run:
```bash
npm install
```

Then to check markdown formatting and test the examples against the JSON schema, you can run:
```bash
npm test
```

This will spit out the same texts that you see online, and you can then go and fix your markdown or examples.

If the tests reveal formatting problems with the examples, you can fix them with:
```bash
npm run format-examples
```
