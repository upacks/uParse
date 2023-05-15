### Hello 👋
Custom Parsers
### Usage
```javascript
import { Start, isNode, isProd, log } from 'utils'
import { UBX, J1939, CSV2JSON, DXF2JSON } from 'uparser'

Start({ 

    onSuccess: (config: {}) => {
        log.info(isNode ? `NodeJS Environment` : `I guess it's Browser :)`)
        log.info(isProd ? `Production Environment` : `I guess it's Development Environment :)`)
    }, 

    onError: (message: string) => {
        log.error(message)
        message.indexOf('fatal') >= 0 ? process.exit() : ":|"
    },

})
```