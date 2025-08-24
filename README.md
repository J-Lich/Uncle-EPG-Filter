# Uncle EPG Filter
A GitHub Actions-powered EPG (Electronic Program Guide) filter that allows you to create a custom EPG XML file based on a list of tvg-ids.
How it Works
This repository uses a Python script and GitHub Actions to automatically fetch EPG data from various sources, filter it based on your custom list of tvg-ids, and then publish a combined, filtered EPG file to your repository. The workflow is set to run automatically to keep your EPG up-to-date.
Features
 * Customizable EPG: Filter EPG data to include only the channels you need.
 * Automated Updates: A GitHub Actions workflow keeps your EPG file updated automatically.
 * M3U8 to tvg-id Extractor: An optional workflow to automatically extract tvg-ids from an M3U8 URL.
 * Extensible: Easily add or remove EPG sources by modifying the Python script.

## How to Use
Follow these steps to set up your own custom EPG filter.
### 1. Fork the Project
First, you'll need to create your own copy of this repository by forking it. Click the Fork button at the top-right of this page.
!(https://i.imgur.com/c3a5Ncb.png)
### 1a. Change Action Permissions
For the automated workflow to update your EPG, you need to grant it read and write permissions.
 * In your forked repository, go to Settings > Actions > General.
 * Scroll down to the "Workflow permissions" section.
 * Select the Read and write permissions option.
 * Click Save.
!(https://i.imgur.com/n739PS6.png)
### 2. Adjust the custom-channels-tvg-ids.txt
This file contains the list of tvg-ids that you want to include in your custom EPG. You can edit this file directly on GitHub. Add or remove tvg-ids, with one tvg-id per line.
### 2a. (Optional) Use the M3U8 tvg-id Extractor
If you have an M3U8 playlist URL and want to automatically generate your custom-channels-tvg-ids.txt from it, you can use the "M3u8 TVGID EXTRACTOR" workflow.
 * In your forked repository, go to the Actions tab.
 * Under "Workflows", click on M3u8 TVGID EXTRACTOR.
 * Click the Run workflow dropdown on the right.
 * Enter your M3U8 URL in the provided field.
 * Click the Run workflow button.
This will run the extractor script and commit the custom-channels-tvg-ids.txt file to your repository.
!(https://i.imgur.com/3jSgN4h.png)

### 3. Copy Your EPG Link
Once the workflow has run successfully, your custom EPG file will be available at the following URL. Simply replace GITHUBUSERNAME with your GitHub username.
> https://raw.githubusercontent.com/**GITHUBUSERNAME**/Uncle-EPG-Filter/main/custom-channels-epg.xml

You can now use this link in any application that supports XMLTV EPG URLs.

## Advanced Customization
You can also customize the Python script (epg_filter.py) to add or remove EPG sources. The sources are defined in a simple list at the top of the script. Feel free to modify this list to suit your needs.

