# Standalone build

Core owns installation/catalog metadata, customer connections and BYOK. The SDK revision and release contract are recorded in standalone.json.

Generate/review/commit Cargo.lock and the validator helper's separate lock when present. Run the qualified rootless build helper with `--check` for locked Cargo checks/tests, then build the default production target. The check stage alone enables declared local provider fixture features; production binaries use default features. Both stages use three Cargo jobs and SDK-revision-scoped caches restricted to trusted Spitzli platform sources.

Core mounts private configuration, issuer keys, mTLS identity, provider credentials and permitted writable storage. Deployment must enforce dropped capabilities, no host network or host socket mounts, no-new-privileges and a read-only root filesystem.

Root native authoring manifests select the validated extension release workflow. Specialized providers and runtimes without a reviewed root manifest select OCI metadata publication only; installation/admission and protocol descriptors remain separate. Test manifests are never promoted. Archives' Core-connected acceptance tests remain in the source monorepo and are listed in standalone.json. UI source is retained separately.
