![Aries-441 · EVA Terminal · Agent Runtime & Sandbox Infrastructure](assets/eva-terminal.webp)

## ![Pilot profile](assets/eva-pilot-profile.webp)

> `AFFILIATION`  Graduate researcher at **IIE, CAS** · B.Eng. in Information Security, **SJTU**
>
> `FOCUS`  Agent runtimes · MicroVM sandboxes · Linux VFS/FUSE · storage volume lifecycles · automated security evaluation
>
> `BLOG`  [aries441.tech ↗](https://aries441.tech/)

## ![Mission log](assets/eva-mission-log.webp)

### [CubeSandbox](https://github.com/TencentCloud/CubeSandbox) · Agent sandbox infrastructure

- **Object storage volumes** · [#2136](https://github.com/TencentCloud/CubeSandbox/pull/2136) · [#2201](https://github.com/TencentCloud/CubeSandbox/pull/2201)\
  Implemented per-volume `private_data` across the API, control plane, storage plugins, and Go/Python/Node.js SDKs for credential-referenced S3/COS bucket and prefix isolation. Added end-to-end lifecycle coverage.
- **virtiofsd / FUSE** · [#2002](https://github.com/TencentCloud/CubeSandbox/pull/2002) · [#2036](https://github.com/TencentCloud/CubeSandbox/pull/2036)\
  Fixed an `s3fs` truncation regression triggered by `xattr` operations. Reused `O_PATH` descriptors via `/proc/self/fd` and isolated each worker’s filesystem context with `unshare(CLONE_FS)`.
- **Control-plane reliability** · [#2236](https://github.com/TencentCloud/CubeSandbox/pull/2236) · [#1988](https://github.com/TencentCloud/CubeSandbox/pull/1988)\
  Enabled `utf8mb4` negotiation for MySQL connections and corrected stale sandbox-route responses from HTTP 500 to 404.

### Jenkins · Security research

Independently reported a missing `Item/Read` permission check in Jenkins queue cancellation. [CVE-2026-53438 / SECURITY-3712](https://www.jenkins.io/security/advisory/2026-06-10/)

## ![Field notes](assets/eva-field-notes.webp)

- **VFS / FUSE** · [一次 xattr 操作如何破坏文件截断语义？](https://aries441.tech/posts/tech-notes/virtiofsd-xattr-truncate/)
- **CPython runtime** · [为什么主线程退出后，ThreadPoolExecutor 的 `submit()` 会报 `interpreter shutdown`？](https://aries441.tech/posts/tech-notes/python-threadpoolexecutor-interpreter-shutdown/)
