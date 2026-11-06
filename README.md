# QRTransf

Transferència òptica de fitxers amb codis QR animats. Una pantalla emet un fitxer dividit en fragments i una altra el reconstrueix amb la càmera.

## Posar en marxa

1. A GitHub, obre **Settings → Pages**.
2. Selecciona **Deploy from a branch**, branca **main**, carpeta **/(root)** i desa.
3. Obre https://aagust11.github.io/qrtransf/ en els dos dispositius.
4. Al primer, selecciona **Emetre**, carrega el fitxer, prem **Preparar** i després **Iniciar**.
5. Al segon, selecciona **Rebre**, activa la càmera, enfoca els QR i descarrega el fitxer quan arribi al 100 % i superi el SHA-256.

## Funcionament i limitacions

- Dades fragmentades en QR amb identificador de sessió i índex; el receptor descarta duplicats.
- Els QR es repeteixen fins que es completa el fitxer, sense necessitat d'internet per enviar-ne el contingut.
- SHA-256 verifica que el fitxer reconstruït és idèntic a l'original.
- El fitxer **no s'envia a cap servidor**; sí que es carreguen les biblioteques QR des de jsDelivr quan s'obre la pàgina.
- La càmera requereix **HTTPS** (GitHub Pages el proporciona) o localhost.
- Els codis QR **no estan xifrats**: no facis servir aquest sistema per a dades confidencials.
- Màxim orientatiu de 25 MiB. Els fitxers grans trigaran molta estona.
- El receptor ha de captar cada QR almenys una vegada; si se'n perd algun, espera la volta següent.
