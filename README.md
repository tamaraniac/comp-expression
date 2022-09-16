# Using Git / Github

To create directory on your computer: 'git clone git@github.com:umich-pcas/comp-expression.git'

All other commands should happen inside the directory, can get there using 'cd comp-expression'

To get new file changes: 'git pull'

To add file changes to Github: 'git add .', 'git commit -m "describe changes here"', 'git push origin main'

# Install Runestone

If you're on Mac, start by installing Homebrew: https://docs.brew.sh/Installation

Next, install python 3 with homebrew: 'brew install python3'

Then, use python 3 to install runestone and pretext: 'pip3 install runestone'

On other systems, install python (look up instructions for your own operating system) and then use python to install runestone: 'pip install runestone'

# Using Runestone

To build changes: 'runestone build'

To serve and preview changes: 'runestone serve' and then go to "http://localhost:8000/index.html" in your browser.
