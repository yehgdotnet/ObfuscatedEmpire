**This project has been merged upstream [to the main Empire project](https://github.com/EmpireProject/Empire). You should probably be using that. This repository will remain here for now, but is not guaranteed to remain updated or stable.**

# ObfuscatedEmpire

ObfuscatedEmpire is a fork of [Empire](https://github.com/EmpireProject/Empire) with [Invoke-Obfuscation](https://github.com/danielbohannon/Invoke-Obfuscation) integrated directly into it's functionality. The main advantage of ObfuscatedEmpire is the ability to establish an in-memory C2 channel that automatically obfuscates all PowerShell run on a target host, which can often help evade AV signatures. For more details on motivations behind the project and to see how it works please refer to [the introductory blog post about it](https://cobbr.io/ObfuscatedEmpire.html) and [the post about the latest updates](https://cobbr.io/ObfuscatedEmpire-Updates.html).

ObfuscatedEmpire also uses [a ScriptBlock logging bypass](https://gist.github.com/cobbr/d8072d730b24fbae6ffe3aed8ca9c407) to avoid creating ScriptBlock logs on target machines.

ObfuscatedEmpire works exactly the same as Empire with added, optional obfuscation settings. All documentation shown below is for Empire. Bug reports are appreciated! Please report any obfuscation-related problems with ObfuscatedEmpire as a Github issue.

# Empire

Empire is a post-exploitation framework that includes a pure-PowerShell2.0 Windows agent, and a pure Python 2.6/2.7 Linux/OS X agent. It is the merge of the previous PowerShell Empire and Python EmPyre projects. The framework offers cryptologically-secure communications and a flexible architecture. On the PowerShell side, Empire implements the ability to run PowerShell agents without needing powershell.exe, rapidly deployable post-exploitation modules ranging from key loggers to Mimikatz, and adaptable communications to evade network detection, all wrapped up in a usability-focused framework. PowerShell Empire premiered at [BSidesLV in 2015](https://www.youtube.com/watch?v=Pq9t59w0mUI) and Python EmPyre premeiered at HackMiami 2016.

To install, run the ./setup/install.sh script. There's also a [quickstart here](http://www.powershellempire.com/?page_id=110) and full [documentation here](http://www.powershellempire.com/?page_id=83).

Empire relies heavily on the work from several other projects for its underlying functionality. We have tried to call out a few of those people we've interacted with [heavily here](http://www.powershellempire.com/?page_id=2) and have included author/reference link information in the source of each Empire module as appropriate. If we have failed to improperly cite existing or prior work, please let us know.

Empire is developed by [@harmj0y](https://twitter.com/harmj0y), [@sixdub](https://twitter.com/sixdub), [@enigma0x3](https://twitter.com/enigma0x3), [rvrsh3ll](https://twitter.com/424f424f), [@killswitch_gui](https://twitter.com/killswitch_gui), and [@xorrior](https://twitter.com/xorrior).

Feel free to join us on Slack! http://adaptiveempire.herokuapp.com/


## Contribution Rules

Contributions are more than welcome! The more people who contribute to the project the better Empire will be for everyone. Below are a few guidelines for submitting contributions.

* Submit pull requests to the [dev branch](https://github.com/powershellempire/Empire/tree/dev). After testing, changes will be merged to master.
* Base modules on the template at [./modules/template.py](https://github.com/PowerShellEmpire/Empire/blob/dev/lib/modules/template.py). **Note** that for some modules you may need to massage the output to get it into a nicely displayable text format [with Out-String](https://github.com/PowerShellEmpire/Empire/blob/0cbdb165a29e4a65ad8dddf03f6f0e36c33a7350/lib/modules/situational_awareness/network/powerview/get_user.py#L111).
* Cite previous work in the **'Comments'** module section.
* If your script.ps1 logic is large, may be reused by multiple modules, or is updated often, consider implementing the logic in the appropriate **data/module_source/*** directory and [pulling the script contents into the module on tasking](https://github.com/PowerShellEmpire/Empire/blob/0cbdb165a29e4a65ad8dddf03f6f0e36c33a7350/lib/modules/situational_awareness/network/powerview/get_user.py#L85-L95).
* Use [approved PowerShell verbs](https://technet.microsoft.com/en-us/library/ms714428(v=vs.85).aspx) for any functions.
* PowerShell Version 2 compatibility is **STRONGLY** preferred. 
* TEST YOUR MODULE! Be sure to run it from an Empire agent before submitting a pull to ensure everything is working correctly.
* For additional guidelines for your PowerShell code itself, check out the [PowerSploit style guide](https://github.com/PowerShellMafia/PowerSploit/blob/master/README.md).
