[![Twitter](https://img.shields.io/badge/Twitter-@Vosough_k-blue.svg?style=flat-square)](https://twitter.com/vosough_k)
[![Linkedin](https://img.shields.io/badge/Linkedin-KiarashVosough-blue.svg?style=flat-square)](https://www.linkedin.com/in/kiarashvosough/)

DocC Github Pages Deploy: Deploy Generated DocC Static Site To Github-Pages.

- [Requirements](#requirements)
- [Usage](#usage)
- [Integration](#integration-with-build-docC-static-site)
- [Contributors](#contributors)
- [License](#license)

## Requirements

| Platform  | Status |
| --- | --- |
|  ubuntu-latest | Tested |

## Usage

See [action.yml](https://github.com/kiarashvosough1999/docC-github-pages-deploy/blob/master/action.yml).

As An Example:

```yml
name: worksapce
on:
  push:
    branches:
      - '**'
jobs:
  build_deploy_site:
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}

    permissions:
      pages: write
      contents: read
      id-token: write

    steps:
    - name: deploy static site
      uses: kiarashvosough1999/docC-github-pages-deploy@added-action-steps
```

> Make Sure give access to `pages`, `contents` and `d-token`, or the action will fail to push the site into Github-Pages.

> Make sure to specify the `name` and `url` on the environment like the example, or the job will fail.


## Integration With Build DocC Static Site

You can use [https://github.com/kiarashvosough1999/build-docC-static-site/tree/master) to generate static site from DocC Archive.

> The default `docC-generated-static-site-uploaded-name` associated with [build-docC-static-site
](https://github.com/kiarashvosough1999/build-docC-static-site/tree/master) and `docC-generated-static-site-zipped-upload-name` associated with this action, input must be the same.

> This action will unzip the input static site with `gtar` and `tar` extension. So do not specify the zip extension on either `docC-generated-static-site-uploaded-name` or `docC-generated-static-site-zipped-upload-name`.
 
## Contributors

Feel free to share your ideas or any other problems. Pull requests are welcomed.

## License

CocoAttributedStringBuilder is released under an MIT license. See [LICENSE](https://github.com/kiarashvosough1999/build-docC-static-site/blob/master/LICENSE) for more information.
