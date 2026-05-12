# Android build branch

This branch exists to produce Android OpenSSL prebuilt artifacts in GitHub Actions.

## What it builds

The workflow `.github/workflows/android-prebuilt.yml` builds these ABIs:

- `arm64-v8a`
- `armeabi-v7a`
- `x86`
- `x86_64`

By default it targets Android API `21` and produces upload artifacts that contain:

- `include/`
- `lib/`
- `ssl/`

When both switches keep their default values, `lib/` contains both shared and static libraries.

## How to run

1. Push branch `android` to your GitHub repository.
2. Open `Actions` -> `Android Prebuilt`.
3. Run the workflow manually, or trigger it by pushing to `android`.

## Notes

- Local Windows builds are not required for this path.
- GitHub Ubuntu runners already provide `perl`, which OpenSSL needs for `Configure`.
- The workflow downloads Android NDK `r26d` automatically.
