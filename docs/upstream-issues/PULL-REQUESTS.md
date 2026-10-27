# Prepared upstream pull requests

Fix branches live on the `0xLattice` forks, ready to submit. Nothing has been
opened against Apple's repositories yet.

| Fix | Branch (fork) | Target | Status |
|---|---|---|---|
| Typed `QUICStreamResetError` on the disconnect path | `0xLattice/swift-nio-quic` → `pr/typed-reset-on-disconnect` | `apple/swift-nio-quic` `main` | ready |
| Fail buffered datagram writes on attach failure (+ regression test) | `0xLattice/swift-nio-quic` → `pr/fail-buffered-datagram-writes` | `apple/swift-nio-quic` `main` | ready |
| No force-unwrap on detached `ProtocolInstanceReference` | `0xLattice/swift-network-evolution` → `fix/no-force-unwrap-detached-instance` | `apple/swift-network-evolution` `main` | ready |
| Expose `HTTP3` and `QPACK` as library products | `0xLattice/swift-nio-http3` → `pr/expose-http3-qpack-products` | `apple/swift-nio-http3` `main` | ready |

PR bodies: use the corresponding issue write-ups in this directory
(01 → typed reset, 02 → datagram writes, 03 → force-unwrap) as the
motivation section; each commit message carries the technical summary. The
HTTP3/QPACK product change is self-explanatory from its commit message: their
types leak through NIOHTTP3's public API but the targets are not products, so
downstream packages can't name them.

The `swift-quic-fixes` branches on all three forks are **integration branches**
(fixes + manifest repoints) that swift-quic pins to; they are not for
upstream submission.
