# Introduction to Markdown

## Overview
**Lorem ipsum** dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

## Why Markdown
**Lorem ipsum** dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. _Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat._ Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

[## Official website ##](https://daringfireball.net/)

# DataCruncher
## Installation
To install DataCruncher, run the following command:
'''bash
import os
from datacrunch import DataCrunchClient

CLIENT_SECRET = os.environ['DATACRUNCH_CLIENT_SECRET']
CLIENT_ID = 'Ibk5bdxV64lKAWOqYnvSi'

datacrunch = DataCrunchClient(CLIENT_ID, CLIENT_SECRET)


ssh_keys = datacrunch.ssh_keys.get()
ssh_keys = list(map(lambda key: key.id, ssh_keys))

instance = datacrunch.instances.create(instance_type='1V100.6V',
                                      image='fastai',
                                      ssh_key_ids=ssh_keys,
                                      hostname='example',
                                      description='example instance')

datacrunch.instances.action(instance.id, datacrunch.constants.instance_actions.DELETE)
'''