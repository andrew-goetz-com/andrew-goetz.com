# Andrew Goetz - Personal Website

Official website: [www.andrew-goetz.com](https://www.andrew-goetz.com)

## Features

### NFC Contact Sharing

This site supports NFC-triggered contact sharing for physical business cards and NFC tags.

- **Landing Page**: [www.andrew-goetz.com/tap](https://www.andrew-goetz.com/tap)
- **vCard File**: [www.andrew-goetz.com/contact/andrew-goetz.vcf](https://www.andrew-goetz.com/contact/andrew-goetz.vcf)

#### How to Use:
1. Write an NFC tag with the URL: `https://www.andrew-goetz.com/tap`
2. When tapped with an iPhone, Safari will open automatically
3. User can tap "Add to Contacts" to save the contact information
4. Works with iOS devices without requiring Shortcuts or additional permissions

#### Technical Details:
- vCard Format: vCard 3.0 (iOS compatible)
- MIME Type: text/vcard (served automatically by GitHub Pages)
- Protocol: HTTPS (required for iOS NFC URL handling)
- Mobile-first design with Matrix theme matching main site

## License

All Rights Reserved © 2024 Andrew Goetz
