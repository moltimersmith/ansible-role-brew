# brew

Common role for macOS hosts that ensures Homebrew is present and then manages:

- taps (`brew tap`)
- formulae (`brew install <formula>`)
- casks (`brew install --cask <cask>`)

## Requirements

- Target host: macOS
- `brew` installed on the target host
- Controller needs the `community.general` collection (the containerized-ansible image includes it).

## Role Variables

```yaml
brew_require_macos: true
brew_update: false
brew_taps: []
brew_formulae: []
brew_casks: []
```

## Example

```yaml
- hosts: macos-local
  roles:
    - role: brew
      vars:
        brew_taps:
          - defenseunicorns/tap
        brew_formulae:
          - uds
```
