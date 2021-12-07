# Augur

[![standard-readme compliant](https://img.shields.io/badge/standard--readme-OK-green.svg?style=flat-square)](https://github.com/RichardLitt/standard-readme)


branch | status
   --- | ---
  main | [![Build Status](https://travis-ci.com/chaoss/augur.svg?branch=main)](https://travis-ci.com/chaoss/augur)
   dev | [![Build Status](https://travis-ci.com/chaoss/augur.svg?branch=dev)](https://travis-ci.com/chaoss/augur)


[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/2788/badge)](https://bestpractices.coreinfrastructure.org/projects/2788)

## What is Augur?

Augur is a software suite for collecting and measuring structured data
about [free](https://www.fsf.org/about/) and [open-source](https://opensource.org/docs/osd) software (FOSS) communities.

We gather trace data for a group of repositories, normalize
it into our data model, and provide a variety of metrics about said
data. The structure of our data model enables us to synthesize data
across various platforms to provide meaningful context for meaningful
questions about the way these communities evolve.

We are a [CHAOSS](https://chaoss.community) project, and many of our
metrics are implementations of the metrics defined by our awesome community. You
can find more information about [how to get involved on the CHAOSS website](https://chaoss.community/participate/).

## Collecting Data

One of Augur's core tenets is a desire to openly gather data that people can trust, and then provide useful and well-defined metrics that help give important context to the larger stories being told by that data. We do this in a variety of ways, one of which is doing all our own data collection in house. We currently collect data from a few main sources:

1. Raw Git commit logs (commits, contributors)
2. GitHub's API (issues, pull requests, contributors, releases, repository metadata)
3. The Linux Foundation's [Core Infrastructure Initiative](https://www.coreinfrastructure.org/) API (repository metadata)
4. [Succinct Code Counter](https://github.com/boyter/scc), a blazingly fast Sloc, Cloc, and Code tool that also performs COCOMO calculations

This data is collected by dedicated data collection workers controlled by Augur, each of which is responsible for querying some subset of these data sources. We are also hard at work building workers for new data sources. If you have an idea for a new one, [please tell us](https://github.com/chaoss/augur/issues/new?template=feature_request.md) - we'd love your input!


## Getting Started

If you're interested in collecting data with our tool, the Augur team has worked hard to develop a detailed guide to get started with our project which can be found [in our documentation](https://oss-augur.readthedocs.io/en/main/getting-started/toc.html).

If you're looking to contribute to Augur's code, you can find installation instructions, development guides, architecture references (coming soon), best practices and more in our [developer documentation](https://oss-augur.readthedocs.io/en/main/development-guide/toc.html). Please know that while it's still rather sparse right now,
but we are actively adding to it all the time. If you get stuck, please feel free to [ask for help](https://github.com/chaoss/augur/issues/new)!

## Database Setup

## Installation 

## Collecting Data

## Augur’s Frontend

#### How to Access the Augur Frontend

**Requirements:**
   - A server
   - A fork of the Augur repository (https://github.com/chaoss/augur) on your local machine

**To make changes to the Augur frontend code:**
In your fork of Augur, go to `frontend → src` to see the various directories and TypeScript files for the frontend.  The majority of the code is found in the files within the `frontend → src → views` directory.

**Steps:**
   1. In your command line, go to the directory of your fork of Augur.
   2. From the Augur directory, go into the directory named “frontend”. If there is not already a file named “frontend.config.json” in this directory, create one and make its content the following:
```
{
    "Frontend": {
        "host": "augur.chaoss.io",
        "port": 5044
    },
    "Server": {
        "cache_expire": "3600",
        "host": "augur.chaoss.io",
        "port": 5044,
        "workers": 12,
        "timeout": 60000
    }
}
```

   3. If you do not already have Node.js and npm installed on your computer, do so now.  It is highly recommended to use a Node version manager like nvm, developed by the OpenJS Foundation, to do this.

   For Linux and macOS users, follow these instructions:
   - https://github.com/nvm-sh/nvm#installing-and-updating

   For Windows users, you may use the above instructions with WSL (Windows Subsystem for Linux), GitBash, or Cygwin.  If you do not use any of these, you may use one of the following alternatives, none of which were developed or are associated with the OpenJS Foundation:
   - https://github.com/coreybutler/nvm-windows (recommended)
   - https://github.com/nullivex/nodist
   - https://github.com/jasongin/nvs
   5. The latest version of Node.js will not work with Augur.  You must use v10.x.  We used v10.24.1. To do this, run the command:  `nvm install 10.24.1` (nvm for Windows may have a different command to do this; see the appropriate GitHub link for help)
   6. Once you have the correct version of Node.js, we want to make sure we have all of Node.js’s related files and packages from the “package-lock.json” directory (located inside the “frontend” directory) installed, just in case they were not already installed.  To do this, run the following command (it may take up to a few minutes to complete):  `npm install`
   7. If you want to make sure that the changes you’ve made to the frontend code will compile into a distributable form before deploying them onto your server, you can create a production build.  To do this, run the following command (it may take up to a few minutes to complete):  `npm run build`
   
   This command will also create a “dist” directory within the “frontend” directory.
   
   8. To see the frontend locally, run the following command:  `npm run serve`

   This command creates a local web server that is hardcoded to not be serviceable on a public domain; it is designed exclusively for local development.  Once this command is  executed, you should see something similar to the following image:
   ![image](https://user-images.githubusercontent.com/70217139/144942802-44502075-0552-4237-94eb-ce00da490f7e.png)
   
   Type the “Local” address (in this case, http://localhost:8080/) into your browser.  You should now be able to see the Augur frontend, as well as any changes you made to the Augur frontend code!


## Command Line Interface

## Contributing

To contribute to Augur, please follow the guidelines found in our [CONTRIBUTING.md](CONTRIBUTING.md) and our [Code of Conduct](CODE_OF_CONDUCT.md). Augur is a welcoming community that is open to all, regardless if you're working on your 1000th contribution to open source or your 1st. We strongly believe that much of what makes open source so great is the incredible communities it brings together, so we invite you to join us!

## License, Copyright, and Funding

Copyright © 2021 University of Nebraska at Omaha, University of Missouri and the CHAOSS Project.

Augur is free software: you can redistribute it and/or modify it under the terms of the MIT License as published by the Open Source Initiative. See the [LICENSE](LICENSE) file for more details.

This work has been funded through the Alfred P. Sloan Foundation, Mozilla, The Reynolds Journalism Institute, contributions from VMWare, Red Hat Software, Grace Hopper's Open Source Day, GitHub, Microsoft, Twitter, Adobe, the Gluster Project, Open Source Summit (NA/Europe), and the Linux Foundation Compliance Summit. Significant design contributors include Kate Stewart, Dawn Foster, Duane O'Brien, Remy Decausemaker, others omitted due to the  memory limitations of project maintainers, and 12 Google Summer of Code Students.
