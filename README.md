# Proton API Bridge

Thanks to Proton open sourcing [proton-go-api][] and the web, iOS, and Android
client codebases, we don't need to completely reverse engineer the APIs by
observing the web client traffic!

[proton-go-api][] provides the basic building blocks of API calls and error
handling, such as 429 exponential back-off, but it is pretty much just a
barebone interface to the Proton API. For example, the encryption and
decryption of the Proton Drive file are not provided in this library. 

The Proton API Bridge,bridges the gap, so software like [rclone][] can be built
on top of this quickly. This codebase handles the intricate tasks before and
after calling Proton APIs, particularly the complex encryption scheme, allowing
developers to implement features for other software on top of this codebase.

Currently, only Proton Drive APIs are bridged, as we are aiming to implement a
backend for [rclone][] while being friendly to other tools that may wish to use
the API.

_**Note** This repository uses a _[friendly-fork][]_ of the [proton-go-api][]. I.e.
Our fork does not break the existing Proton Go API, and all changes are
actively submitted back upstream._

## More information
- [License](LICENSE)
- [Contributing](CONTRIBUTING.md)
- [Roadmap](Roadmap.md)

[//]: # (References)

[proton-go-api]: https://github.com/ProtonMail/go-proton-api
[friendly-fork]: https://github.com/major0/go-proton-api
[rclone]: https://github.com/rclone/rclone
