[bep]: https://github.com/bep
[bugs]: https://github.com/gohugoio/hugo/issues?q=is%3Aopen+is%3Aissue+label%3ABug
[contributing]: CONTRIBUTING.md
[create a proposal]: https://github.com/gohugoio/hugo/issues/new?labels=Proposal%2C+NeedsTriage&template=feature_request.md
[documentation repository]: https://github.com/gohugoio/hugoDocs
[documentation]: https://gohugo.io/documentation
[dragonfly bsd, freebsd, netbsd, and openbsd]: https://gohugo.io/installation/bsd
[forum]: https://discourse.gohugo.io
[friends]: https://github.com/gohugoio/hugo/graphs/contributors
[go]: https://go.dev/
[hugo modules]: https://gohugo.io/hugo-modules/
[installation]: https://gohugo.io/installation
[issue queue]: https://github.com/gohugoio/hugo/issues
[linux]: https://gohugo.io/installation/linux
[macos]: https://gohugo.io/installation/macos
[prebuilt binary]: https://github.com/gohugoio/hugo/releases/latest
[requesting help]: https://discourse.gohugo.io/t/requesting-help/9132
[spf13]: https://github.com/spf13
[static site generator]: https://en.wikipedia.org/wiki/Static_site_generator
[support]: https://discourse.gohugo.io
[themes]: https://themes.gohugo.io/
[twitter]: https://twitter.com/gohugoio
[website]: https://gohugo.io
[windows]: https://gohugo.io/installation/windows

<a href="https://gohugo.io/"><img src="https://raw.githubusercontent.com/gohugoio/gohugoioTheme/master/static/images/hugo-logo-wide.svg?sanitize=true" alt="Hugo" width="565"></a>

A fast and flexible static site generator built with love by [bep], [spf13], and [friends] in [Go].

---

## Project Overview

Hugo allows you to create static websites with ease, enabling you to focus on writing content without the complexity of managing databases or servers. It uses a simple file structure and Markdown or HTML content to generate a fully functional static website.

## Prerequisites

Before you begin, make sure you have the following prerequisites installed on your system:

1. Hugo: You can download and install Hugo from the official website (https://gohugo.io/getting-started/installing/). Make sure to check that Hugo is correctly installed by running hugo version in your terminal.

2. Git (optional): If your project is hosted in a Git repository, ensure you have Git installed on your system.

## Getting Started

**Clone the Project:** Clone the repository to your local machine.

**View Local Site:** Run a local server to preview your site:

```
hugo server -D
```

The -D flag includes drafts if any. Open your web browser and visit http://localhost:1313 to view your site locally.

**Build the Site:** When you are satisfied with your site, build it using the following command:

```
hugo
```

This will generate static HTML files in the public directory.

**Deployment:** Deploy the generated public directory to your web server, or use a web hosting service that supports static websites.

## Further Reading

For more in-depth documentation and advanced features of Hugo, visit the official Hugo website: https://gohugo.io/documentation/

Happy coding and building beautiful static websites with Hugo!