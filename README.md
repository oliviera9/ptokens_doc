# pTokens bridge JSON-RPC Specification

[View the spec][playground]

The pTokens JSON-RPC is a collection of methods that all bridges implement.

## Building

The specification is split into multiple files to improve readability. It
can be compiled the spec into a single document as follows:

```console
$ npm install
$ npm run build
Build successful.
```

This will output the file `openrpc.json` in the root of the project. This file
will have all schema `#ref`s resolved.

## Contributing

The specification is written in [OpenRPC][openrpc]. Refer to the
OpenRPC specification and the JSON schema specification to get started.

### Testing

There are currently three tools for testing contributions. The main two that
run as GitHub actions are an [OpenRPC validator][validator] and a
[spellchecker][spellchecker]:

```console
$ npm install
$ npm run lint
OpenRPC spec validated successfully.

$ pip install pyspelling
$ pyspelling -c spellcheck.yaml
Spelling check passed :)
```

The third tool can validate a live JSON-RPC provider against the specification:

```console
$ ./scripts/debug.sh https://pbtconbsc-node-1a.eu.ngrok.io/v2/pbtc-on-bsc/ app_queryReport \"native\",2
data.json valid
```

## License

This repository is licensed under [CC0](LICENSE).


[playground]: https://playground.open-rpc.org/?schemaUrl=https://raw.githubusercontent.com/oliviera9/ptokens_doc/assembled-spec/openrpc.json&uiSchema[appBar][ui:splitView]=false&uiSchema[appBar][ui:input]=false&uiSchema[appBar][ui:examplesDropdown]=false&uiSchema[appBar][ui:title]=pTokens&uiSchema[appBar][ui:logoUrl]=https://avatars.githubusercontent.com/u/16259422?s=200&v=4
[openrpc]: https://open-rpc.org
[validator]: https://open-rpc.github.io/schema-utils-js/globals.html#validateopenrpcdocument
[spellchecker]: https://facelessuser.github.io/pyspelling/
