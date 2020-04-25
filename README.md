---
noteId: "ff9fe180872111eaad338b3c6e277d62"
tags: []

---

# SSHHeatmap
Generates a heatmap of IP's that made failed SSH login attempts on linux systems, using /var/log/auth.log to get failed attempts. Uses the ipinfo.io library to fetch the IP address coordinates, and folium to generate the heatmap.

<img src="https://i.imgur.com/ZNoACD0.png"></img>

## Dependencies
- Python >3.5
- folium
- ipinfo
- requests

```bash
pip3 install folium requests ipinfo
````



## Installation & Usage

Use wget (or curl, or git clone) to download the script.
```bash
wget https://raw.githubusercontent.com/meesaltena/SSHHeatmap/master/SSHHeatmap.py
```

Use grep tot generate a text file that contains the logging entries of failed ssh connection attempts.
```bash
grep "Failed password" /var/log/auth.log > failed_attempts.txt
```
Get a free [ipinfo](https://ipinfo.io/) api key.

Run the script, passing the required arguments.
```bash
python3 SSHHeatmap.py failed_attempts.txt <ipinfo_api_key>
```

You can pass additional arguments to set the minimum number of login attempts required for the ip to be included in the heatmap, and the file name to use for the heatmap. 

```bash
python3 SSHHeatmap.py <sourcefile> <api key> <min_attempts> <heatmap_filename>
```

Open the generated heatmap HTML file in a browser.


## License
[MIT](https://choosealicense.com/licenses/mit/)
