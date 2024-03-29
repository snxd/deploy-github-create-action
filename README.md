# Solsta Create Action for GitHub

This project is a GitHub Action that uses Solid State Networks tools and services to create or modify Solsta products, environments, or repositories.

The action is compatible with Windows, Linux, and OSX runners.  Windows self-hosted runners require git-bash (https://git-scm.com/) in the %PATH%.

## Variables

* **solsta_client_id:** Client ID to authenticate usage of Solid State Networks console tools
* **solsta_client_secret:** Secret Key to authenticate usage of Solid State Networks console tools
* **console_version:** Version of Solsta Console Tools to use
* **scripts_version:** Version of Solsta Deploy Scripts to use
* **action_type:**  Either create, or update
* **object_type:**  Either product, repository, or environment to create/update 
* **target_product:**  Target product to create/update (case-sensitive)
* **target_environment:**  Target environment create/update to(case-sensitive)
* **target_repository:**  Target repository create/update to (case-sensitive)
* **description**  Friendly description of the modified object
* **publish_location:**  Environment publish location URI
* **source_location:**  Environment source location URI
* **update_path_count:**  Environment update path count number

## Using

Here is an example YAML Fragment in the steps section of a build:

```yaml
    steps:
    - name: Create Object Configuration
      uses: snxd/deploy-github-create-action@v3
      with:
        console_version: '6.1.2.84'
        scripts_version: '3.8.2'
        solsta_client_id:  ${{ secrets.SOLSTA_CLIENT_ID }}
        solsta_client_secret:  ${{ secrets.SOLSTA_CLIENT_SECRET }}
        action_type: create
        object_type: product 
        target_product: My Product Name
        description:  Friendly description of My Product
```

## License
(C) 2022 Solid State Networks, LLC.  All Rights Reserved.
