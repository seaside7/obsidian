
## Recommendation

Since you have appVersionSource: "local":

1. Keep managing versions in app.json

2. Increment versionCode for every build

3. Update version when you make meaningful changes

4. Use the EAS website to view/download builds (optional)


   eas secret:create --scope project --name EXPO_PUBLIC_API_URL --value "https://q0luzxueb8.execute-api.us-east-1.amazonaws.com/prod" --type string


eas build --platform android --profile preview


eas secret:delete --name EXPO_PUBLIC_API_URL
eas secret:create --scope project --name EXPO_PUBLIC_API_URL --value "new-url" --type string


eas env:create --name EXPO_PUBLIC_API_URL --value "new-url" --scope project


eas env:list


https://expo.dev/accounts/seasideiskandar/projects/smallbiz-admin/builds/6a72dc7e-56cf-4256-9cf7-054ad495231a


npm run build:android:preview


eas update over the air




## Workflow

### Scenario 1: JavaScript/UI changes (most common)

1. Make your code changes

2. Run: npm run update:production

3. Users get the update automatically (usually within minutes)

### Scenario 2: Native changes (less common)

1. Make your changes

2. Run: npm run build:android:production

3. Users need to install the new APK

## Important notes

1. Runtime version: Uses appVersion policy — updates go to apps with the same version

2. Automatic checking: App checks for updates on startup

3. Channels: Preview and production use separate update channels

4. First build: The first APK must include expo-updates (already configured)

## Test it

1. Make a small UI change (e.g., change a text color)

2. Run: npm run update:production

3. Wait 1-2 minutes

4. Restart the app — you should see the change


smallbiz

6281234567890

need this format