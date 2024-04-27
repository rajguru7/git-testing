**Steps**
1. Clone sample repo on which to test domain-catcher
2. Download dc-demo script at root of git repo
3. Run the script
    * It will create a .dc.json file with the allowlist of domains
4. Update .dc.json with the deployment type as below:
    ```json
    {
      "catcher": {
        "build_time": [],
        "run_time": [
          "www.google.com",
          "github.com"
        ]
      },
      "enforcer": {
        "value": true,
        "run_time": {
          "environment": "kubernetes",
          "cni": "cilium",
          "deployment_namespace": "",
          "deployment_label": "app: url-fetcher"
        },
        "build_time": {}
      }
    }
    ```
5. Run the script again
    * It will create a cilium network policy to allow only the domains in the
      allowlist
    * It will create a github action to update the allowlist on every push
