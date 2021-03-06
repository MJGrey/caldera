[![Release](https://img.shields.io/badge/dynamic/json?color=blue&label=Release&query=tag_name&url=https%3A%2F%2Fapi.github.com%2Frepos%2Fmitre%2Fcaldera%2Freleases%2Flatest)](https://github.com/mitre/caldera/releases/latest)
[![Build Status](https://travis-ci.com/mitre/caldera.svg?branch=master)](https://travis-ci.com/mitre/caldera)
[![codecov](https://codecov.io/gh/mitre/caldera/branch/master/graph/badge.svg)](https://codecov.io/gh/mitre/caldera)
[![Documentation Status](https://readthedocs.org/projects/caldera/badge/?version=stable)](http://caldera.readthedocs.io/?badge=stable)

# CALDERA

*Full documentation, training and use-cases can be found [here](https://caldera.readthedocs.io/en/latest/)*

CALDERA is a cyber security framework designed to easily run autonomous breach-and-simulation exercises. It can also be used to run manual red-team engagements or automated incident response.

It is built on the [MITRE ATT&CK™ framework](https://attack.mitre.org/) and is an active research project at MITRE.

The framework consists of two components:

1) **The core system**. This is the framework code, consisting of what is available in this repository. Included is 
an asynchronous command-and-control (C2) server with a REST API and a web interface. 
2) **Plugins**. These are separate repositories that hang off of the core framework, providing additional functionality. 
Examples include agents, GUI interfaces, collections of TTPs and more. 

## Plugins
- **[Access](https://github.com/mitre/access)** (red team initial access tools and techniques)
- **[Atomic](https://github.com/mitre/atomic)** (Atomic Read Team project TTPs)
- **[Builder](https://github.com/mitre/builder)** (dynamically compile payloads)
- **[Compass](https://github.com/mitre/compass)** (ATT&CK visualizations)
- **[GameBoard](https://github.com/mitre/gameboard)** (visualize joint red and blue operations)
- **[Human](https://github.com/mitre/human)** (create simulated noise on an endpoint)
- **[Manx](https://github.com/mitre/manx)** (shell functionality and reverse shell payloads)
- **[Mock](https://github.com/mitre/mock)** (simulate agents in operations)
- **[Response](https://github.com/mitre/response)** (incident response)
- **[Sandcat](https://github.com/mitre/sandcat)** (default agent)
- **[SSL](https://github.com/mitre/SSL)** (enable https for caldera)
- **[Stockpile](https://github.com/mitre/stockpile)** (technique and profile storehouse)
- **[Training](https://github.com/mitre/training)** (certification and training course)

## Requirements

These requirements are for the computer running the core framework:

* Any Linux or MacOS
* Python 3.6.1+ (with Pip3)
* Google Chrome is our only supported browser
* Recommended hardware to run on is 8GB+ RAM and 2+ CPUs

## Installation

Start by cloning this repository recursively, passing the desired version/release in x.x.x format. This will pull in all available plugins. If you clone master - or any non-release branch - you may experience bugs.
```Bash
git clone https://github.com/mitre/caldera.git --recursive --branch x.x.x 
```

Next, install the PIP requirements:
```Bash
pip install -r requirements.txt
```
> Additionally, you can run our [install script](https://caldera.readthedocs.io/en/latest/Install-script.html) which will install several more dependencies that super-power your CALDERA server instance.

Finally, start the server. 
```Bash
python server.py
```
You can now navigate to 127.0.0.1:8888 in a browser and log in as either a red or blue team member. 
Caldera will generate randomized passwords when started for the first time.
You can find these credentials in the console logs the first time caldera starts or in the `conf/local.yml` file.
You can also customize the default accounts or create new credentials by editing the `conf/local.yml`.
Once you have everything running, we highly recommend going through the Training plugin to learn the ins-and-outs of the framework.

If you're using caldera in a development or test environment, you can start the server with insecure
default credentials:

```
# Start caldera with insecure default creds (admin:admin, red:admin, blue:admin)
python server.py --insecure
```

> There is also a [Docker image](https://caldera.readthedocs.io/en/latest/Docker-deployment.html) for CALDERA.

## Video tutorial

Watch the [following video](https://www.youtube.com/watch?v=_mVGjqu03fg) for a brief run through of how to run your first operation. 

## Contributing
Refer to our [contributor documentation](CONTRIBUTING.md)

## Licensing

In addition to CALDERA's open source capabilities, MITRE maintains several in-house CALDERA plugins that offer 
more advanced functionality. For more information, or to discuss licensing opportunities, please reach out to 
caldera@mitre.org or directly to [MITRE's Technology Transfer Office](https://www.mitre.org/about/corporate-overview/contact-us#technologycontact).
