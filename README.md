# @slater/theme
A skeleton theme for getting started with Slater.

Full docs [here](https://github.com/the-couch/slater).

## License
MIT License © [The Couch](https://thecouch.nyc)

# shopify-starter
1. Download or clone this repo to your computer
2. Create a Private App in your Shopify Store
    1. Apps
    2. Scroll all the way down to "Working with a developer on your shop? __Manage private apps__"
    3. Create a new Private App, and make sure under the Admin API Permissions, __Theme__ is set to Read & Write access
3. If you are going to reuse your old theme, I would duplicate your production theme, then download the theme, then move all the files over into the `/src` of this starter
4. If you start from scratch, just find the Debbut Theme or a super simple theme from the marketplace, and then use that as the development theme.
5. Duplicate the `slater.config.test.js` file, and rename it to `slater.config.js`

```
const path = require('path')

module.exports = {
  themes: {
    development: {
      id: '',  <---- Online Store > Themes > Customize Theme and plucking the ID from the URL i.e. ../admin/themes/<id>/editor 
      password: '', <---- Password from the Private App you just created in step #2
      store: '', <---- Your <STORE>.myshopify.com
      ignore: [
        'settings_data.json' // leave this here to avoid overriding theme settings on sync
      ]
    }
  }
}
```

6. Then run `npm install`
7. Then to deploy your empty starter run `npm run deploy:development`, and it will just deploy all the files locally up to that theme. 
8. To develop run `npm run start`, then go to `https://localhost:4000/` and allow permissions to create an SSL certificate.
9. After that above, you should be able to edit files and then refresh the preview link of that theme and see your changes. 
10.Then again, when you like what you have, run `npm run deploy:development` to deploy that theme.
