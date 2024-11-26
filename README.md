# ttbplugin plugin for [Tutor](https://docs.tutor.edly.io)

ttbplugin plugin for Tutor. This is used to initialize the Google Firebase credentials in the Open edX platform.
The actual credentials are stored in Github secrets and are injected into the Open edX platform during the deploy process.

Adds the following settings to the Open edX platform:

- `GOOGLE_FIREBASE_SERVICE_ACCOUNT_JSON`. see [https://console.cloud.google.com/iam-admin/serviceaccounts](https://console.cloud.google.com/iam-admin/serviceaccounts?project=ttb-android&supportedpurview=project)
- `GOOGLE_FIREBASE_CONFIG_JSON`
- `GOOGLE_FIREBASE_DATABASE_URL`
- `TOASTR_CUSTOM_CSS_URL`. Defaults to [https://ttb-mumbai-prod-storage.s3.ap-south-1.amazonaws.com/static/css/push-notifications.css](https://ttb-mumbai-prod-storage.s3.ap-south-1.amazonaws.com/static/css/push-notifications.css)
- `MFE_CONFIG['GOOGLE_FIREBASE_CONFIG']`. see [https://app.turnthebus.org/api/mfe_config/v1](https://stage.turnthebus.org/api/mfe_config/v1)
- `MFE_CONFIG['TOASTR_CUSTOM_CSS_URL']`. see [https://app.turnthebus.org/api/mfe_config/v1](https://stage.turnthebus.org/api/mfe_config/v1)

`GOOGLE_FIREBASE_CONFIG_JSON` is of the form:

```python
DEFAULT_FIREBASE_CONFIG = {
  "apiKey": "YOUR_API_KEY",
  "authDomain": "YOUR_AUTH_DOMAIN",
  "projectId": "YOUR_PROJECT_ID",
  "storageBucket": "YOUR_STORAGE_BUCKET",
  "messagingSenderId": "YOUR_MESSAGING_SENDER_ID",
  "appId": "YOUR_APP_ID"
}
```

## Installation

```console
pip install git+https://github.com/Turn-The-Bus/tutor-contrib-ttbplugin
```

## Usage

```console
tutor plugins enable ttbplugin
tutor config save --set TTB_GOOGLE_FIREBASE_SERVICE_ACCOUNT_JSON='{}'
                  --set TTB_GOOGLE_FIREBASE_CONFIG_JSON='{}'
                  --set TTB_GOOGLE_FIREBASE_DATABASE_URL='https://somewhere.com'
                  --set TTB_TOASTR_CUSTOM_CSS_URL='https://ttb-mumbai-prod-storage.s3.ap-south-1.amazonaws.com/static/css/push-notifications.css'
```
