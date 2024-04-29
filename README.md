# VMware Harbor Registry Documentation

This repo contains the content for the documentation for VMware Harbor Registry.

The content in this repo publishes to the VMWare Harbor Registry documentation site at https://docs.vmware.com/en/VMware-Harbor-Registry/services/vmware-harbor-registry/GUID-index.html.

The subnav for this documentation is located at https://github.com/pivotal-cf/docs-book-pcfservices/blob/master/master_middleman/source/subnavs/vmware-harbor_subnav.erb.

## How To Contribute

Please help us improve the accuracy and completeness of the VMware Harbor Registry documentation by contributing.

The easiest way to contribute is to file a pull request through GitHub.

Every topic in the [VMware Harbor Registry documentation](https://docs.vmware.com/en/VMware-Harbor-Registry/services/vmware-harbor-registry/GUID-index.html) has a corresponding file in this repo. Locate the correct file and make a pull request against it. You can also navigate to the topic and click "View the source for this page in GitHub" at the bottom of the topic.

## How To Use Bookbinder To View Your Docs

[Bookbinder](https://github.com/pivotal-cf/bookbinder/blob/master/README.md) is a command-line utility for stitching Markdown docs into a hostable web app. The PCF Docs Team uses Bookbinder to publish our documentation sites, but you can also use Bookbinder to view a live version of your documentation on your local machine.

Bookbinder draws the content for the site from this repo, the left navigation menu ("subnav") from [`docs-book-pcfservices`](https://github.com/pivotal-cf/docs-book-partners/blob/master/master_middleman/source/subnavs/vmware-harbor_subnav.erb), and various layout configuration and assets from [`docs-layout-repo`](https://github.com/pivotal-cf/docs-layout-repo).

To use Bookbinder to view your documentation, perform the following steps:

1. Clone this repo to the `~/workspace` directory on your local machine.
1. Clone [`docs-book-pcfservices`](https://github.com/pivotal-cf/docs-book-pcfservices) and [`docs-layout-repo`](https://github.com/pivotal-cf/docs-layout-repo) to the `~/workspace` directory on your local machine.
1. Change into the `docs-book-pcfservices` directory.
1. Run `bundle install` to install all of the necessary gems, including Bookbinder.
1. Build your documentation site with `bookbinder` in one of the two following ways:
    * Run `bundle exec bookbinder watch` to build an interactive version of the docs and navigate to `localhost:4567/myservice/` in a browser. (It may take a moment for the site to load at first.) This builds a site from your content repo at `docs-content`, and then watches that repo to update the site if you make any changes to the repo.
    * Run `bundle exec bookbinder bind local` to build a Rack web-app of the book. After the bind has completed, `cd` into the `final_app` directory and run `rackup`. Then navigate to `localhost:9292/myservice/` in a browser.

### Troubleshooting

If, after running `bundle exec bookbinder watch` and navigating to `localhost:4567/myservice/`, you see the message "Error compiling CSS asset" related to the `font-awesome-sass` library, do the following:

1. Open the `Gemfile`.
1. Add the line `gem 'font-awesome-sass', "4.7.0"`.
1. Save the `Gemfile`.
1. Run `bundle update`. 

To view the locally built book for this repository, use the following URL: `http://localhost:4567/vmware-harbor/index.html`. 
