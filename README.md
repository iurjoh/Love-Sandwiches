# Love Sandwiches automation

[Português (Brasil)](README.pt-BR.md)

## Idea and process

A Python course exercise for six sandwich sales values, surplus and suggested next stock using Google Sheets. Source reviewed on 2026-10-01. The implemented function sequence records the workflow; no dated personal plan or design diary was found in the reviewed files.

## Architecture and design

`run.py` authorizes a service account from local creds.json and opens a sheet named love_sandwiches. It collects six comma-separated integers, appends sales, calculates surplus from the latest stock row, appends surplus, averages the last five sales entries per column and adds 10% before rounding and appending stock. The interface is terminal text. The accompanying Node package is the Code Institute browser-terminal wrapper.

## Setup precautions

Do not run or import run.py just to inspect it: authorization happens at module load and main() runs immediately. It writes to sales, surplus and stock worksheets. This README update did not retrieve credentials, connect to Sheets, read business records or execute the program.

Use only a separately authorized disposable sheet and synthetic values if testing later. requirements.txt pins gspread 5.6.0 and historical Google auth packages. The script requests spreadsheets, drive.file and broad Drive scopes; review the minimum required access before any credential setup. Keep persistent service-account secrets outside source control and screenshots. No current hosted deployment was verified.

## Testing and limitations

No automated suite was found in the reviewed root listing. The validator requires exactly six integers but accepts negatives. Stock calculations assume existing numeric rows, consistent columns and non-empty sales history. Test invalid input, missing sheets, empty/short history, header rows, rounding and API failures using mocks or a disposable sheet. Writes are separate append operations; retrying after partial failure can duplicate rows. Refactor import-time effects before isolated unit tests. No test result is claimed.

## Snapshots

No screenshot was verified or added. Future terminal captures under `docs/assets/` must use synthetic numbers and hide credentials, sheet identifiers and business data. Record actual commands/results rather than inventing successful updates.

## Credits and licensing

Course/template and dependency rights remain unchanged. The existing package manifest declares ISC; no new license is added or applied to third-party material.

---

## Original README

![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)

Welcome Iuri Johansson,

This is the Code Institute student template for deploying your third portfolio project, the Python command-line project. The last update to this file was: **August 17, 2021**

## Reminders

* Your code must be placed in the `run.py` file
* Your dependencies must be placed in the `requirements.txt` file
* Do not edit any of the other files or your code may not deploy properly

## Creating the Heroku app

When you create the app, you will need to add two buildpacks from the _Settings_ tab. The ordering is as follows:

1. `heroku/python`
2. `heroku/nodejs`

You must then create a _Config Var_ called `PORT`. Set this to `8000`

If you have credentials, such as in the Love Sandwiches project, you must create another _Config Var_ called `CREDS` and paste the JSON into the value field.

Connect your GitHub repository and deploy as normal.

## Constraints

The deployment terminal is set to 80 columns by 24 rows. That means that each line of text needs to be 80 characters or less otherwise it will be wrapped onto a second line.

-----
Happy coding!
