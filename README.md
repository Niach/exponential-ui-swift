# ExponentialUI 0.1.1

The SwiftUI renderer of the Exponential UI SDK: A2UI surfaces streamed from
any server, painted natively on iOS 17+ and macOS 14+ at the frames the Rust
core computes. Docs, the catalog, themes and the host API:
**https://ui.exponential.at**.

```swift
// Package.swift
.package(url: "<this repository>", from: "0.1.1")
// target
.product(name: "ExponentialUI", package: "exponential-ui-swift")
```

```swift
import ExponentialUI

let host = ExponentialHost(HostOptions(transport: JSONLStreamTransport(url: URL(string: "https://example.com/a2ui.jsonl")!)))
host.connect()
// in a view
ScrollView { HostSurface(host: host, surfaceId: "main") }
```

| product | what |
|---|---|
| `ExponentialUI` | the painter + the host API (`ExponentialHost`, transports, `HostSurface`) |
| `ExponentialUIPrimitives` | the generic SwiftUI primitives the catalog natives are painted with |

Licence: see LICENSE and NOTICE. Generated from the Exponential monorepo
(`packages/exponential-ui-swift`); issues and changes go there.
