# Increment Environment Variable

This is a GitHub Action that increments an environment variable.
If environment variable does not exist, it will create it and set it to 1.

## Usage
```YAML 
- name: Increment Environment Variable
  uses:  MandalAutomations/Increment-Environment-Variable@v1
  with:
    Name: "Name for the variable to increment"
    EnvironmentName: "Environment Name"
    RepoId: ${{ github.repository_id }}
    Token: ${{ secrets.PAT_TOKEN }}
```
### Increment variable in multiple environments use matrix
```YAML 
increment:
    runs-on: ubuntu-latest
    strategy:
        matrix:
            enviornments: ["ev1", "ev2", "ev3"]
    steps:
        - name: Increment Environment Variable
          uses:  MandalAutomations/Increment-Environment-Variable@v1
          with:
            Name: "Name for the variable to increment"
            EnvironmentName: ${{ matrix.enviornments }}
            RepoId: ${{ github.repository_id }}
            Token: ${{ secrets.PAT_TOKEN }}
```

## Inputs
### Name: 
`Required` `String` Name for the variable to increment

### EnvironmentName: 
`Required` `String` Environment Name

### RepoId: 
`Required` `String` Repository ID can be found using  ${{ github.repository_id }}

### Token: 
`Required` `String` Personal Access Token (PAT)
