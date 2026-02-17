## Wayback Machine iOS App

Official iOS app for the Internet Archive's Wayback Machine, allowing users to save and browse archived web pages.

**Original Repository:** https://github.com/internetarchive/wayback-machine-ios

### Features

- Save web pages to the Wayback Machine
- Browse archived versions of websites
- View availability calendars for archived pages
- Upload media files to Internet Archive
- Safari extension support

### Requirements

- iOS 12.0 or later
- Xcode 11.0 or later
- CocoaPods

### Install Dependencies

```bash
sudo gem install cocoapods
pod install
```

**Important:** Always open `WM.xcworkspace` (not `WM.xcodeproj`) after running `pod install`.

### Building the App

1. Clone the repository
2. Run `pod install` in the project directory
3. Open `WM.xcworkspace` in Xcode
4. Select the `WM` scheme
5. Build and run (⌘R)

### Project Structure

- `WM/` - Main iOS application target
- `WayBackMachine/` - Safari Extension target  
- `WMTests/` - Unit tests
- `WMUITests/` - UI tests

### Dependencies

- **Alamofire** (~4.9) - Networking library (Note: Consider upgrading to 5.x for security updates)
- **MBProgressHUD** (1.1.0) - Progress indicators
- **FRHyperLabel** - Hyperlink text labels
- **UITextView+Placeholder** (~1.2) - Placeholder support for text views
- **IQKeyboardManagerSwift** - Keyboard management

### Troubleshooting

#### Pod Install returns an error?

Try editing **Podfile** and remove or comment out targets 'WMTests' and 'WMUITests'. (which should have already been done...)


#### *IQKeyboardManager* framework not compiling?

Try this quick fix in XCode:

Pods > IQKeyboardManagerSwift (dropdown) > Build Settings > Build Options > Require Only App-Extension-Safe API > Set to NO

### Security Notes

- Credentials should be stored in iOS Keychain, not UserDefaults
- Never log sensitive information (API keys, passwords, tokens) in production
- Consider using environment-based configuration for API endpoints

### Contributing

Contributions are welcome! Please ensure:
- Code follows Swift best practices
- Remove deprecated iOS patterns
- Add unit tests for new features
- Update documentation as needed

### License

Please refer to the original repository for license information.

