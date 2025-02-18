<p><b>AlphaDroid for Redmi Note 8/8T (gingko/willow)</b></p>

<p>AlphaDroid is a custom ROM for Android, based on LineageOS/crDroid, with a new look and some extra features and optimizations. Extra features are picked from other custom ROMs and adapted to our needs or implemented by us.</p>

### Sync ###

```bash

# Initialize local repository
repo init -u https://github.com/alphadroid-project/manifest -b alpha-15.1 --git-lfs

# Clone local manifest for Redmi Note 8/8T
git clone https://github.com/mnasibzade/local_manifest -b alpha-15.1 .repo/local_manifests

# Sync
repo sync
```

### Build ###

```bash

# Set up environment
$ . build/envsetup.sh

# Build the code
$ lunch alpha_ginkgo-<build_variant>
$ make bacon

# Or, instead of 'lunch + make', just
$ brunch alpha_<device_codename>-<build_variant>
```

<p>
  If you need help to create a build environment, you can check crDroid instructions <a href="https://github.com/crdroidandroid/android">here</a>.
</p>
