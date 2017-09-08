# F5 BIG-IP Controller for Cloud Foundry Experimental Buildpack

A custom experimental [buildpack](http://docs.cloudfoundry.org/buildpacks/) for F5 BIG-IP Controller for Cloud Foundry.

This is based on the [Cloud Foundry python buildpack](https://github.com/cloudfoundry/python-buildpack).

### Building the Buildpack

1. Make sure you have fetched submodules

  ```bash
  git submodule update --init
  ```

1. Get latest buildpack dependencies

  ```shell
  BUNDLE_GEMFILE=cf.Gemfile bundle
  ```

1. Build the buildpack

  ```shell
  BUNDLE_GEMFILE=cf.Gemfile bundle exec buildpack-packager [ --uncached | --cached ]
  ```

1. Use in Cloud Foundry

    Upload the buildpack to your Cloud Foundry and optionally specify it by name

    ```bash
    cf create-buildpack custom_python_buildpack python_buildpack-cached-custom.zip 1
    cf push my_app -b custom_python_buildpack
    ```
