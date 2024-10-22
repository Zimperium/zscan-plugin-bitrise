# zscan-plugin-bitrise

## Bitrise.io step for uploads to zScan

This plugin can be used to upload mobile applications to Zimperium (zScan) to be scanned for vulnerabilities. Using a plugin simplifies integrating mobile application security testing into CI/CD process and enables detection and remediation of vulnerabilities earlier in the application SDLC.

For more information on zScan, please see [Continuous Mobile Application Security Scanning](https://www.zimperium.com/zscan/).

## Prerequisites

1. Zimperium [MAPS](https://www.zimperium.com/mobile-app-protection/) license that includes zScan functionality.
2. API credentials with permissions to upload binaries
3. A valid application binary (.ipa, .apk, etc.), either built by the current pipeline or otherwise accessible by the plugin.

## Parameters

### Mandatory

These parameters are mandatory, unless a default value is available as described below.

- **Endpoint**: console base URL, e.g., `https://ziap.zimperium.com/`
- **Client ID** and **Client Secret**: API credentials that can be obtained from the console. You are required to use a [Bitrise Secret](https://devcenter.bitrise.io/en/builds/secrets.html) for the Client Secret part. We recommend using a [Bitrise Secret](https://devcenter.bitrise.io/en/builds/secrets.html) for the Client ID part as well.
- **File Path**: the path to the binary, either absolute or relative to the current workspace
- **Report Format**: the format of the scan report, either 'json' (default) or 'sarif'
- **Team Name**: name of the team to which this application belongs.  This is required only if submitting the application for the first time; values are ignored if the application already exists in the console and assigned to a team.  If not supplied, the application will be assigned to the 'Default' team.

### Optional

At this time, there are no optional parameters that can be specified in the step configuration.

## Usage

Please refer to the Bitrise.io [documentation](https://devcenter.bitrise.io/en/steps-and-workflows/introduction-to-steps/adding-steps-to-a-workflow.html) for details on adding steps to a workflow.  This step can found in the Bitrise [Step Library](https://github.com/bitrise-io/bitrise-steplib).

## License

This plugin is licensed under the MIT License. By using this plugin, you agree to the following terms:

```text
MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## Enhancements

Submitting improvements to the plugin is welcomed and all pull requests will be approved by Zimperium after review.
