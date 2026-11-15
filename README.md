# session-auth

Sesioetan oinarritutako autentifikazioaren adibidea: Express, express-session eta bcryptjs.

Bi adar daude:

- `basic`: erabiltzaileak memorian gordetzen dira.
- `main`: erabiltzaileak eta sesioak MongoDBn gordetzen dira.

Adar honetan: Erabiltzaileak memorian gordetzen dira (zerbitzaria berrabiaraztean galtzen dira).

## Behar dena

- Node.js 18 edo berriagoa

## Abiarazi

```bash
npm ci
node app.js
```

Ireki http://localhost:3000.

## Segurtasun oharrak

- Pasahitzak bcryptjs-ekin hasheatuta gordetzen dira, inoiz ez testu lauan.
- Login-ak mezu bera ematen du erabiltzailea ez badago eta pasahitza okerra bada, erregistratutako erabiltzaileak ez agerian uzteko.
- `saveUninitialized: false`: sesioa (eta cookiea) saioa hasi ondoren bakarrik sortzen da.
- Erabiltzaile-izena HTMLan sartu aurretik ihes egiten da (XSS saihesteko).
- Sesioaren sekretua (`your-secret-key`) adibide bat da: benetako proiektu batean ingurune-aldagai batetik irakurri behar da.
