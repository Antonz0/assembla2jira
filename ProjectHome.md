## Overview ##
This is a LUA script I created for migrating tickets for our project from [Assembla.com](http://www.assembla.com/home) service backup dumps to [Atlassian JIRA](http://www.atlassian.com/software/jira/). Currently it uses [JIRA Jelly](https://confluence.atlassian.com/display/JIRA/Jelly+Tags) as an intermediate script format.

## Disclaimer and Release Notes ##
This project was written to do one-time conversion of project dump from Assembla.com format to Atlassian JIRA. I'm not against Assembla.com or adept of JIRA, I just wanted that work to be done, when our project migrated from Assembla to Atlassian tools because of changed ownership and company policies.

I'm not expecting to support this project actively, because probably I will not need it anymore in near time. I hope it will be helpful for someone who needs similar task to be done. So you can take it and use it as is, or try to extend and change it as you want. If you want to continue supporting and extending this script - tell me and I'll add you to team. Please note that if you planning to extend this script you better to consider migrating it to some other API instead of Jelly, like [REST](http://docs.atlassian.com/jira/REST/latest/) interactive API. It's because JIRA almost deprecated Jelly and SOAP APIs in favor of REST, and also Jelly support in JIRA has many quirks. Read FAQ section and TODO notes for more details.

## Download ##
Download assembla2jira-1.0.zip from [Downloads section](http://code.google.com/p/assembla2jira/downloads/list).

## Documentation ##
  * [Installation](Installation.md)
  * [Configuration File](ConfigurationFile.md)
  * [Conversion Process](ConversionProcess.md)

## TODO list ##
  * Migrate output part to [JIRA REST](http://docs.atlassian.com/jira/REST/latest/) APIs (interactive) with log storage for incomplete imports, allowing to do re-export run.
  * Support all custom fields (probably requires REST API support first, as this is very quirky and inconvenient in Jelly).
  * Support migrating attachments (also requires REST API).
  * Support conversion of work logging and estimates (probably requires REST API or heavy Jelly access to Jira classes).

## History ##
### 1.0 (2012-07-07) ###
  * Initial release.