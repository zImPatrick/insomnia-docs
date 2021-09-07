---
layout: article-detail
title:  FAQ
category: Support
category-url: support
---

Here are the answers to the most frequently asked questions that we receive. For support, see our [support community page](https://insomnia.rest/support). 

## General Questions
<hr>

The following are general questions we frequently get about Insomnia. 

### What platforms does Insomnia run on?

Insomnia has desktop apps for 64-bit versions of Mac, Windows, and Linux.

### Does Insomnia provide 32-bit binaries?

At this time, Insomnia is 64-bit only.

### What software license does Insomnia use?

The Insomnia desktop application and related software packages are open source software under the MIT license and the source code is available at github.com/kong/insomnia. The server-side software that backed the paid sync service is closed source.

### Can I use Insomnia for commercial use?

Yes, of course!

### How can I support Insomnia?

First of all, thank you! Since Insomnia is just starting out, the best thing you can do is help spread the word! You can also submit bug reports on our open source repository, let us know how you use Insomnia, or sign up for a paid plan.

### Does Insomnia have a EULA agreement?

Currently there is no EULA that is provided for Insomnia. As of now we only have our [Terms of Service](https://insomnia.rest/terms) and [Privacy Policy](https://insomnia.rest/privacy).

Currently we consider the [MIT](https://opensource.org/licenses/MIT) license as a EULA but we are looking to change this in the future.

### What is the team size limit for a free trial?

The free trial is limited to 5 team members. Once the trial has expired you will be billed for each team member, which means the post-trial limit is the number of member seats you purchase.

### How do I increase the number of seats on my team?

In order to add more people, the team owner needs to first update the subscription to include more seats. This can be simply accomplished by going to the Insomnia dashboard, located at https://app.insomnia.rest, then select Account -> Change Subscription, and then increase the "Team Size" as needed. You will be billed accordingly on your next statement.

### How can I customize receipt data?

It is often necessary to include company information on receipts. For example, to include the company name, address, or VAT number. 

{:.alert .alert-primary}
**Note**: Invoice data will only appear on downloaded invoices, not invoices received by email.

Additional information can be specified when [Creating or Updating a Subscription](https://app.insomnia.rest/app/subscribe/). Any changes to this information will appear on any invoices downloaded from the [Invoice History](https://app.insomnia.rest/app/invoices/) page.

### Why do I have multiple charges on my plan?

When you notice that there are dual, or multiple, charges for your Insomnia plan. This is because some banks may display charge attempts as multiple entries when the currency differs. Our payment provider (Stripe) will only attempt to charge your designated payment method once.

## Technical Questions
<hr>

These technical questions commonly come up when user interact with Insomnia. 

### My app is not responding. What should I do?

Sometimes, if you make a request that returns a lot of data, Insomnia will become unresponsive. If this happens, you can manually delete the large response file by doing the following.

1. Locate the Application Data Folder

    You can find the application data folder in the Help menu. If the help menu is not accessible, here are the default paths for each operating system.

    `%APPDATA%` on Windows
    `$XDG_CONFIG_HOME` or `~/.config` on Linux
    `~/Library/Application Support` on macOS

2. Delete the Offending Response Body

    Each response stores the body inside its own file in the "responses" folder. Locate the large responses and delete them, then restart Insomnia.

    It's safe to delete responses. Insomnia will simply report that it cannot locate the body.

### How can I temporarily disable Nunjucks template?

You can disable templating of the request body via the request settings dialog (accessed from the sidebar). For more control, you can also disable templating by wrapping the desired content in the Nunjucks {% raw %}{% raw %}{% endraw %} Tag.

### Why don’t I see anything after importing a backup?

The import/export feature acts similarly to copying files in a filesystem. If the import contains data that originated from your application, data will be overwritten. However, if the import contains data that did not originate from your application, new data (including request collections / design documents) may have be created.

{:.alert .alert-primary}
**Note**: You can check for newly created Collections and Documents on the Dashboard.

### Where does the application store data?

Insomnia stores data in Electron’s appData directory, which differs depending on platform. The local database is distributed across files with the name `insomnia.${resourceName}.db`.

* `%APPDATA%/Insomnia` on Windows
* `XDG_CONFIG_HOME/Insomnia` or `~/.config/Insomnia` on Linux
* `~/Library/Application Support/Insomnia` on macOS

The app data directory can also be shown by navigating to Help > Show App Data Folder.

### Where does the application store logs?

Insomnia stores logs in the following location, depending on the platform:

* `%APPDATA%/Insomnia/logs` on Windows
* `$XDG_CONFIG_HOME/Insomnia/logs` or `~/.config/Insomnia/logs` on Linux
* `~/Library/Logs/Insomnia` on macOS

You can open the parent folder, by navigating to Help > Show App Logs Folder in Insomnia.

### Where do I find keyboard shortcuts?

A list of all keyboard shortcuts can be found within the application under Preferences > Keyboard.

### Where does Insomnia store environment information on a Linux (snap) install?

Various forms of user data, log files and environment information — the kind of data that’s generated and consumed by applications during operations can be located in the `/var/snap/` directory. Additionally, the `~/snap` directory that exists in a user’s home directory will contain directories using some of the names seen in `/var/snap`. These directories are meant to store versioned data related to settings used by your user account.