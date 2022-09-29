# Winston Developer Documentation

## File Structure : 
```
-Winston
-- apps
-- assets
-- bin
-- builds
-- classes
-- configs
-- coverage
-- docs
-- node_modules
-- tests
-- translations
```
> [Emoji Token Assets](./Emoji_Token_Assets.md)

The root `.env` file has some optional settings to bootstrap **Winston**.

```env
MONGO_SERVER=mongodb+srv://{URLLINK}
MONGO_USER=NONE
MONGO_PASS=NONE
GOOGLE_API_KEY={GOOGLE_API_KEY}
```

The application `.env` file is located in the subfolder of the application. i.e `/app/bots/Dev/.env`

Dev Bot `.env` file.
```env
MODE=dev
#MODE=sandbox
#MODE=production
DEBUG_MESSAGES=false
#DEBUG_MESSAGES=false
SERVICE_CONFIGS="/configs"
```

Teaching Winston is all about adding the right information to the right sections of his application.


```JSON
{

}
```


```JavaScript
{

}
```
