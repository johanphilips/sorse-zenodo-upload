# sorse-zenodo-upload


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
