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
/home/flolu/.cache/bazel/_bazel_flolu/84119ced1a20b2c977a2817bf0e2d608/sandbox/linux-sandbox/181/execroot/repro/bazel-out/host/bin/external/npm/protoc-gen-ts/bin/protoc-gen-ts.sh.runfiles/npm/node_modules/typescript/lib/typescript.js:11851
        return array.hasOwnProperty("pos") && array.hasOwnProperty("end");
                     ^

TypeError: Cannot read property 'hasOwnProperty' of null
    at Object.isNodeArray (/home/flolu/.cache/bazel/_bazel_flolu/84119ced1a20b2c977a2817bf0e2d608/sandbox/linux-sandbox/181/execroot/repro/bazel-out/host/bin/external/npm/protoc-gen-ts/bin/protoc-gen-ts.sh.runfiles/npm/node_modules/typescript/lib/typescript.js:11851:22)
    at createNodeArray (/home/flolu/.cache/bazel/_bazel_flolu/84119ced1a20b2c977a2817bf0e2d608/sandbox/linux-sandbox/181/execroot/repro/bazel-out/host/bin/external/npm/protoc-gen-ts/bin/protoc-gen-ts.sh.runfiles/npm/node_modules/typescript/lib/typescript.js:20082:25)
    at Object.createCallExpression (/home/flolu/.cache/bazel/_bazel_flolu/84119ced1a20b2c977a2817bf0e2d608/sandbox/linux-sandbox/181/execroot/repro/bazel-out/host/bin/external/npm/protoc-gen-ts/bin/protoc-gen-ts.sh.runfiles/npm/node_modules/typescript/lib/typescript.js:21335:95)
    at Object.createCall (/home/flolu/.cache/bazel/_bazel_flolu/84119ced1a20b2c977a2817bf0e2d608/sandbox/linux-sandbox/181/execroot/repro/bazel-out/host/bin/external/npm/protoc-gen-ts/bin/protoc-gen-ts.sh.runfiles/npm/node_modules/typescript/lib/typescript.js:2814:29)
    at createToObject (/home/flolu/.cache/bazel/_bazel_flolu/84119ced1a20b2c977a2817bf0e2d608/sandbox/linux-sandbox/181/execroot/repro/bazel-out/host/bin/external/npm/protoc-gen-ts/bin/protoc-gen-ts.sh.runfiles/npm/node_modules/protoc-gen-ts/index.js:49:14)
    at createMessage (/home/flolu/.cache/bazel/_bazel_flolu/84119ced1a20b2c977a2817bf0e2d608/sandbox/linux-sandbox/181/execroot/repro/bazel-out/host/bin/external/npm/protoc-gen-ts/bin/protoc-gen-ts.sh.runfiles/npm/node_modules/protoc-gen-ts/index.js:1016:5)
    at processMessageDescriptor (/home/flolu/.cache/bazel/_bazel_flolu/84119ced1a20b2c977a2817bf0e2d608/sandbox/linux-sandbox/181/execroot/repro/bazel-out/host/bin/external/npm/protoc-gen-ts/bin/protoc-gen-ts.sh.runfiles/npm/node_modules/protoc-gen-ts/index.js:1545:5)
    at processProtoDescriptor (/home/flolu/.cache/bazel/_bazel_flolu/84119ced1a20b2c977a2817bf0e2d608/sandbox/linux-sandbox/181/execroot/repro/bazel-out/host/bin/external/npm/protoc-gen-ts/bin/protoc-gen-ts.sh.runfiles/npm/node_modules/protoc-gen-ts/index.js:1590:12)
    at main (/home/flolu/.cache/bazel/_bazel_flolu/84119ced1a20b2c977a2817bf0e2d608/sandbox/linux-sandbox/181/execroot/repro/bazel-out/host/bin/external/npm/protoc-gen-ts/bin/protoc-gen-ts.sh.runfiles/npm/node_modules/protoc-gen-ts/index.js:1680:24)
    at Object.<anonymous> (/home/flolu/.cache/bazel/_bazel_flolu/84119ced1a20b2c977a2817bf0e2d608/sandbox/linux-sandbox/181/execroot/repro/bazel-out/host/bin/external/npm/protoc-gen-ts/bin/protoc-gen-ts.sh.runfiles/npm/node_modules/protoc-gen-ts/index.js:1765:1)
--ts_out: protoc-gen-ts: Plugin failed with status code 1.
```
