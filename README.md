set VAULT_ADDR=http://docker:8200

vault.exe init

Initializing a vault:

vault init
vault unseal <secret 1>
vault unseal <secret 2>
vault unseal <secret 3>
Authorizing using the root token:

vault auth <root token>

vault.exe write secret/hello value=world
vault.exe read -format=json secret/hello

There is a tool called jq that can be used to pull out values from the json result set

https://stedolan.github.io/jq/

vault.exe read -format=json secret/hello | C:\Users\stone\Downloads\jq-win64.exe -r .data.value

curl -H "X-Vault-Token:a26cada1-fc6f-a844-ac53-b38f4c6cfc11" -XGET http://docker:8200/v1/secret/hello

curl -X POST -H "X-Vault-Token: a26cada1-fc6f-a844-ac53-b38f4c6cfc11" -H "Content-Type: application/json"  -d '{"username":"Test", "password":"Test"}' "http://docker:8200/v1/secret/service"