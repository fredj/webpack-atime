```
# installation
git clone git@github.com:fredj/webpack-atime.git
cd webpack-atime/
npm i

# change access time to 01/01/2018 12:00
touch -t 201801011200 node_modules/webpack-cli/bin/opencollective.js

# simulate a read only filesystem
sudo chattr +i node_modules/webpack-cli/bin/opencollective.js

# try to build
npm run build

# Error: EPERM: operation not permitted

# cleanup
sudo chattr -i node_modules/webpack-cli/bin/opencollective.js
```
