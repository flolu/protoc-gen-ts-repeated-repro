`repeated` properties with custom types don't work.

## Setup

```
yarn install
yarn build
```

throws:

```
ERROR: /home/flolu/Desktop/protoc-gen-ts-repeated-repro/BUILD.bazel:11:17: Generating Protocol Buffers for Typescript //:car failed (Exit 1) protoc failed: error executing command bazel-out/host/bin/external/com_google_protobuf/protoc '--plugin=protoc-gen-ts=bazel-out/host/bin/external/npm/protoc-gen-ts/bin/protoc-gen-ts.sh' '--ts_out=bazel-out/k8-fastbuild/bin' ... (remaining 2 argument(s) skipped)

Use --sandbox_debug to see verbose messages from the sandbox
/node_modules/typescript/lib/typescript.js:11851
        return array.hasOwnProperty("pos") && array.hasOwnProperty("end");
                     ^

TypeError: Cannot read property 'hasOwnProperty' of null
    at Object.isNodeArray (/node_modules/typescript/lib/typescript.js:11851:22)
    at createNodeArray (/node_modules/typescript/lib/typescript.js:20082:25)
    at Object.createCallExpression (/node_modules/typescript/lib/typescript.js:21335:95)
    at Object.createCall (/node_modules/typescript/lib/typescript.js:2814:29)
    at createToObject (/node_modules/protoc-gen-ts/index.js:49:14)
    at createMessage (/node_modules/protoc-gen-ts/index.js:1016:5)
    at processMessageDescriptor (/node_modules/protoc-gen-ts/index.js:1545:5)
    at processProtoDescriptor (/node_modules/protoc-gen-ts/index.js:1590:12)
    at main (/node_modules/protoc-gen-ts/index.js:1680:24)
    at Object.<anonymous> (/node_modules/protoc-gen-ts/index.js:1765:1)
--ts_out: protoc-gen-ts: Plugin failed with status code 1.
```
