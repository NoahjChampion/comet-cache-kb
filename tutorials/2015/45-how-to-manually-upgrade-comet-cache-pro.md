---
title: How to Manually Upgrade Comet Cache Pro
categories: tutorials
tags: installation-upgrade
author: raamdev
github-issue: https://github.com/websharks/comet-cache-kb/issues/45
toc-enable: off
---

In most cases, you can follow the [Comet Cache Pro Installation](https://cometcache.com/pro-installation/) instructions the first time and then configure the Pro Plugin Updater (**WordPress Dashboard → Comet Cache → Plugin Updater**) to keep Comet Cache Pro updated. However, some web hosts block the Pro Plugin Updater from working correctly, resulting in [a 404 error](https://cometcache.com/kb-article/why-am-i-getting-a-404-error-when-running-the-pro-updater/).

If you cannot get your web host to work correctly with the Pro Plugin Updater, or if you have some other scenario that requires you to manually update Comet Cache, then you can follow the instructions below to manually upgrade Comet Cache Pro whenever an update is available.

## Step-by-Step: Upgrading Comet Cache Pro Manually

1. [Log into cometcache.com](https://cometcache.com/wp-login.php) to download the latest version of Comet Cache Pro.

     ![2015-02-04_18-20-37](https://cloud.githubusercontent.com/assets/1563559/6054499/92df2702-ac9a-11e4-8b91-c1a85a1f4d5c.png)

2. Visit your [My Account page at cometcache.com](http://cometcache.com/account/), where you may now obtain the latest version of Comet Cache Pro. Please download the `comet-cache-pro.zip` file from this page.

     ![2015-02-05_05-04-05](https://cloud.githubusercontent.com/assets/1563559/6061450/795993b2-acf4-11e4-802e-5d969a651662.png)

3. Now before manually upgrading Comet Cache Pro, we should make sure that your existing Comet Cache options remain preserved. Visit **WordPress Dashboard → Comet Cache → Plugin Options → Plugin Deletion Safeguards** and make sure that "Safeguard my options and the cache" is selected.

     ![2015-03-19_12-54-37](https://cloud.githubusercontent.com/assets/53005/6736074/0102d11a-ce39-11e4-8536-a50b880455db.png)
     ![2015-03-19_12-56-06](https://cloud.githubusercontent.com/assets/53005/6736083/07335348-ce39-11e4-8de2-1fb4d537e55d.png)

4. Now we need to **Deactivate** and then **Delete** the old Comet Cache Pro plugin so that we can install the new version. As long as the Plugin Deletion Safeguards are enabled (see previous step), you will not lose any of your existing Comet Cache Options in this step.

     ![2015-03-19_12-57-44](https://cloud.githubusercontent.com/assets/53005/6736111/346f5960-ce39-11e4-9269-b6361d54fba9.png)
     ![2015-03-19_12-58-22](https://cloud.githubusercontent.com/assets/53005/6736114/361e6800-ce39-11e4-8916-2b569e3651c5.png)
     ![2015-03-19_12-58-41](https://cloud.githubusercontent.com/assets/53005/6736115/37f41134-ce39-11e4-904f-4b5d9b25b01b.png)

5. Once the old version has been deleted, you can upload and activate the latest version of Comet Cache Pro, which you downloaded earlier. Visit **WordPress Dashboard → Plugins → Add New** to upload and install the new version of Comet Cache Pro.

     ![2015-03-19_12-59-16](https://cloud.githubusercontent.com/assets/53005/6736137/58e42e38-ce39-11e4-9601-46567c76b03d.png)

6. Now upload and activate the `comet-cache-pro.zip` (or it might be named something like: `comet-cache-pro-vXXXXXX.zip`) file that you downloaded from cometcache.com. You can upload the ZIP file using your WordPress Dashboard; i.e. **Dashboard → Plugins → Add New → Upload Plugin**. _See attached screenshots for example._

     ![2015-02-05_05-08-28](https://cloud.githubusercontent.com/assets/1563559/6061535/11454c70-acf5-11e4-8439-2fcd036da63b.png)
     ![2015-02-05_05-15-30](https://cloud.githubusercontent.com/assets/1563559/6061673/0e38bbb0-acf6-11e4-8cfd-eab2e564583a.png)
     ![2015-02-05_05-16-39](https://cloud.githubusercontent.com/assets/1563559/6061701/39386180-acf6-11e4-904a-57ae77088b55.png)

7. Once Comet Cache Pro has been activated, you can confirm that you now have the latest version by looking at the version number and comparing that to the latest release at the top of [the changelog](http://cometcache.com/changelog/).

     ![2015-03-19_13-06-20](https://cloud.githubusercontent.com/assets/53005/6736261/17e69c76-ce3a-11e4-909b-31449632d72e.png)