## Mongoose Encryption

1. *install:* npm install mongoose-encryption --save
2. *import module:* 
 - `global.encrypt = require('mongoose-encryption');`
3. *generate two keys:* openssl rand -base64 32; openssl rand -base64 64;
4. *key as global:* 
 - global.encKey = 32bytes;
 - global.sigKey = 64bytes;
5. *set encrypt in each scheme:* 
 - `userSchema.plugin(encrypt, { global.encryptionKey: global.encKey, signingKey: global.sigKey });`
6. *CLEAN THE BANK*
