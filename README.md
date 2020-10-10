# Remove DNS Record Action for GitHub

Removes a CloudFlare DNS record by ID or record name.

## Usage via Github Actions

Add [CLOUDFLARE_TOKEN](https://developers.cloudflare.com/api/tokens/create) and CLOUDFLARE_ZONE to the [repository secrets](https://docs.github.com/en/actions/configuring-and-managing-workflows/creating-and-storing-encrypted-secrets).

```yaml
name: example
on:
  pull_request:
    type: [closed]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: scottrocha/remove-dns-record@v2
        with:
          name: "review.example.com"
          token: ${{ secrets.CLOUDFLARE_TOKEN }}
          zone: ${{ secrets.CLOUDFLARE_ZONE }}
```

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE).
