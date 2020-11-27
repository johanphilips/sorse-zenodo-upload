# sorse-zenodo-upload

# Assumptions
- If you do not supply a `token` with `--token <TOKEN>`, the script takes enviroment variable `ZENODO_API_TOKEN` or `ZENODO_SANDBOX_API_TOKEN` to connect to Zenodo or its Sandbox (if `--sandboxing` is provided).
- .md files have frontmatter corresponding to the SORSE format. Currently only basic checks are done, such as the presence of `title` and `affiliations` fields.
- If any goes wrong for a particular event item (.md file), the script stops processing this file, but continues with the next one. The process will not be backtracked and possibly a partial Zenodo deposition remains. Check the log file for more information.

# Installation
- docker
- pip install -r requirements.txt

# Usage

```sh
$ python sorse-zenodo-upload.py --help
usage: SORSE Zenodo Upload script. This script will browse recursively through INPUTPATH and look for .md files that match the format of the SORSE events.
       [-h] [--sandboxing] --inputpath INPUTPATH [--outputpath OUTPUTPATH]
       [--overwrite] [--token TOKEN] [--communityid COMMUNITYID] [--publish]

optional arguments:
  -h, --help            show this help message and exit
  --sandboxing          If supplied, Zenodo Sandbox will be used instead.
  --inputpath INPUTPATH
                        The root folder for the input files.
  --outputpath OUTPUTPATH
                        the root folder for the output files, containing the
                        doi. If omitted, INPUTPATH will be used.
  --overwrite           If supplied, DOIs will be added inline to input files.
  --token TOKEN         If not provided in .env as ZENODO_TOKEN (or
                        ZENODO_SANDBOX_TOKEN), you can supply the Zenodo Token
                        here.
  --communityid COMMUNITYID
                        Community ID to be used in Zenodo.
  --publish             If supplied, depositions will be published as well.
```

The script will create a log file `sorse-zenodo-upload.log` in the current directory
