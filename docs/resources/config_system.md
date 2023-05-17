# Resource: harbor_config_system

## Example Usage

```hcl
resource "harbor_config_system" "main" {
  project_creation_restriction = "adminonly"
  robot_token_expiration       = 30
  robot_name_prefix            = "harbor@"
  scanner_skip_update_pulltime = true
}
```

## Argument Reference

The following arguments are supported:

* **project_creation_restriction** - (Optional) Who can create projects within Harbor. Can be **"adminonly"** or **"everyone"**

* **robot_token_expiration** - (Optional) The amount of time in days a robot account will expiry. 

* **robot_name_prefix** - (Optional) Robot account prefix.

* **scanner_skip_update_pulltime** - (Optional) Allows preventing that vulnerability scanners will update the last pull time for an image.
`NOTE: "scanner_skip_update_pulltime" can only be used with harbor version v2.8.0 and above`

`NOTE: If the time is set to high you will get a 500 internal server error message when creating robot accounts`
