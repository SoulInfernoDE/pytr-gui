# pyTR GUI: Use TradeRepublic in terminal with a gui

This is a gui for the marzzzello's pytr app. I am not affiliated with Trade Republic Bank GmbH.

## Installation

Install with `pip3 install pytr`

Or you can clone the repo like so:

```sh
git clone https://github.com/SoulInfernoDE/pytr-gui.git
cd pytr-gui
pip3 install .
```

## Original pytr Usage

```
$ pytr help
usage: pytr [-h] [-v {warning,info,debug}] [-V]
            {help,login,dl_docs,portfolio,details,get_price_alarms,set_price_alarms,export_transactions,completion}
            ...

Use "pytr command_name --help" to get detailed help to a specific command

Commands:
  {help,login,dl_docs,portfolio,details,get_price_alarms,set_price_alarms,export_transactions,completion}
                         Desired action to perform
    help                 Print this help message
    login                Check if credentials file exists. If not create it
                         and ask for input. Try to login. Ask for device reset
                         if needed
    dl_docs              Download all pdf documents from the timeline and sort
                         them into folders. Also export account transactions
                         (account_transactions.csv) and JSON files with all
                         events (events_with_documents.json and
                         other_events.json
    portfolio            Show current portfolio
    details              Get details for an ISIN
    get_price_alarms     Get overview of current price alarms
    set_price_alarms     Set price alarms based on diff from current price
    export_transactions  Create a CSV with the deposits and removals ready for
                         importing into Portfolio Performance
    completion           Print shell tab completion

Options:
  -h, --help             show this help message and exit
  -v {warning,info,debug}, --verbosity {warning,info,debug}
                         Set verbosity level (default: info)
  -V, --version          Print version information and quit

```

## GUI Usage

```
$ pytr

starts pytr with Gooey gui
```

same as cli usage but it's a little bit visual...


## Authentication

There are two authentication methods:

- Web login (default)
- App login

Web login is the newer method that uses the same login method as [app.traderepublic.com](https://app.traderepublic.com/), meaning you receive a token in the TradeRepublic app or via SMS.

App login is the older method that uses the same login method as the TradeRepublic app.
First you need to perform a device reset - a private key will be generated that pins your "device". The private key is saved to your keyfile. This procedure will log you out from your mobile device.


pytr will look for them in the file `~/.pytr/credentials` (the first line must contain the phone number, the second line the pin). If the file doesn't exist pytr will ask for for the phone number and pin.

All credits for the pytr app goes to @marzzzello i only did some gui additions and renamed some lines to pyTR GUI so that it is visible that it is an modified main.py
