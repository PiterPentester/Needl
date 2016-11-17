# Needl

**Take back your privacy. Lose yourself in the haystack.**

Your ISP is most likely tracking your browsing habits and selling them to marketing agencies (albeit anonymised). Or worse, making your browsing history available to law enforcement at the hint of a Subpoena. **Needl** will generate legitimate random Internet traffic in order to conceal your "real" traffic, essentially making your data the **Needl**e in the haystack. The goal is to make it harder for your ISP, government, etc to track your browsing habits.

![Demo](https://pbs.twimg.com/media/CxeQsH5XAAAp_vN.jpg:large)

**On 16th November 2016 the UK's IP Bill passed parliament and is set to become law. ISPs will be required to keep a 12-month web history and bulk collection of your data.**

Implemented modules:

- **Google**: generates a random search string, searches Google and clicks on a random result.
- **Alexa**: visits a website from the Alexa Top 1 Million list.
- **Twitter**: generates a popular English name and visits their profile; performs random keyword searches
- **DNS**: produces random DNS queries.

Modules in the roadmap (_feel free to get stuck in_):

- **WhatsApp**
- **Spotify**
- **Facebook Messenger**

**Warning**: the Alexa list contains a lot of porn websites. If this is of concern then don't use Needl until adult content filtering is added.

## Installation

Needl will work on pretty much any Linux system with Python 3.0+. A simple `sudo apt-get install python3 python3-pip` will take all of your troubles away.

You can then install Needl in 4 simple steps:

1. `cd /opt`
2. `git clone https://github.com/eth0izzle/needl.git`
3. `sudo make install` or `sudo pip3 install -r requirements.txt`
4. `python3 needl.py --daemon` _(todo: [write service scripts](https://github.com/eth0izzle/needl/issues/1))_

## Usage

Needl runs as a daemon and will happily sit in the background chomping away 24/7, 365. Each module (task) has scheduled actions, for example random DNS queries will happen every 60 seconds. You can configure the intervals within `./data/settings.yaml`.

    usage: needl.py [-h] [--datadir DATADIR] [-d] [-v] [--logfile LOGFILE]
                    [--pidfile PIDFILE]
    
    Take back your privacy. Lose yourself in the haystack.
    
    optional arguments:
      -h, --help         show this help message and exit
      --datadir DATADIR  Data directory
      -d, --daemon       Run as a deamon
      -v, --verbose      Increase logging
      --logfile LOGFILE  Log to this file. Default is stdout.
      --pidfile PIDFILE  Save process PID to this file. Default is /tmp/needl.pid.
                         Only valid when running as a daemon.

## F.A.Qs

1. **Why not just use a VPN/Tor?**
And you should! We suggest using **Needl** alongside. Slap it on a Raspberry Pi and let it do it's thing.

2. **Can [insert service here] differentiate between Needl and legitimate requests?**
In theory, yes. [insert service here] can track you with Cookies or Session data. Needl will tackle this in the future.

3. **Where are your tests?!?**
Submit a pull request. _Please_.

## Contributing

Check out the [issue tracker](https://github.com/eth0izzle/needl/issues) and see what tickles your fancy.

1. Fork it, baby!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

## History

**v0.1**
First release

## License

MIT. See LICENSE