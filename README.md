# Solsta Create Action for GitHub

This project is a GitHub Action that uses Solid State Networks tools and services to create or modify Solsta products, environments, or repositories.

The action is compatible with Windows, Linux, and OSX runners.  Windows self-hosted runners require git-bash (https://git-scm.com/) in the %PATH%.

## Variables

* **solsta_client_id:** Client ID to authenticate usage of Solid State Networks console tools
* **solsta_client_secret:** Secret Key to authenticate usage of Solid State Networks console tools
* **console_version:** Version of Solsta Console Tools to use
* **scripts_version:** Version of Solsta Deploy Scripts to use
* **create_type:**  Either product, repository, or environment to create/modify 
* **target_product:**  Target product to create/modify (case-sensitive)
* **target_environment:**  Target environment create/modify to(case-sensitive)
* **target_repository:**  Target repository create/modify to (case-sensitive)
* **description**  Friendly description of the modified object
* **alias_location:**  Environment alias location URI
* **catalog_location:**  Environment catalog location URI
* **metafile_location:**  Environment metafile location URI
* **publish_location:**  Environment publish location URI
* **source_location:**  Environment source location URI
* **storage_type:**  Environment storage type options are piece, pieceshared, or file
* **update_path_count:**  Environment update path count number

## Using

Here is an example YAML Fragment in the steps section of a build:

```yaml
    steps:
    - name: Create Object Configuration
      uses: snxd/deploy-github-create-action@v2
      with:
        console_version: '6.1.2.84'
        scripts_version: '3.7.31'
        solsta_client_id:  ${{ secrets.SNXD_CLIENT_ID }}
        solsta_client_secret:  ${{ secrets.SNXD_CLIENT_SECRET }}
        create_type: product 
        target_product: My Product Name
        description:  Friendly description of My Product
```

## License
(C) 2022 Solid State Networks, LLC.  All Rights Reserved.
