## CORS�Ƃ�

CORS�iCross-Origin Resource Sharing, �I���W���ԃ��\�[�X���L�j�́A���g�̃I���W�����猩���A�ʂ̃I���W���i�N���X�I���W���j����̃��N�G�X�g�������邩���肷��d�g�݂ł��B

�Ⴆ�΁Awww.example.com����擾����javascript�̃t�@�C�����Aapi.example.com�Ƃ���API��AJAX���N�G�X�g�𑗂��ď����擾����P�[�X���l�����ꍇ�Aapi.example.com��API��CORS�Ή����Ă��Ȃ��ꍇ�AWeb�u���E�U�����Z�L�����e�B�@�\�ł���SOP�i����I���W���|���V�[ Same Origin Policy�j�ƌĂ΂��d�g�݂ɂ��Aapi.example.com��AJAX���N�G�X�g�̓u���b�N����Ă��܂��܂��B

���N�G�X�g���u���b�N����Ȃ����߂ɂ́Aapi.example.com����CORS�̐ݒ������K�v������܂��B

## SOP�ᔽ�̗�

CORS���K�v�ƂȂ闝�R�̓u���E�U�Ɏ������ꂽSOP�̎d�g�݂��N���X�I���W�����N�G�X�g���u���b�N���邽�߂ł��BSOP������I���W���Ƃ݂Ȃ������͈ȉ��ɂȂ�܂��B
- ����v���g�R��
- ����h���C��
- ����|�[�g

���L�P�[�X�̏ꍇ�ASOP�Ɉᔽ���Ȃ����߂ɂ�AJAX���N�G�X�g��URI��
- �v���g�R���FHTTPS
- �h���C���Fwww.example.com
- �|�[�g�F443

�ł��邱�Ƃ������ƂȂ�܂����AAJAX���N�G�X�g��URI�̃h���C����api.example.com�ɂȂ��Ă��邽�߁ASOP�ᔽ�ƂȂ�AAJAX���N�G�X�g�����M�ł��܂���B

```mermaid
sequenceDiagram
    autonumber
    actor ���[�U
    participant browser as �u���E�U
    participant web�T�[�o as www.example.com
    participant api as api.example.com
    ���[�U->>browser: URL���́ihttps://www.example.com�j
    browser->>web�T�[�o: www.example.com
    web�T�[�o-->>browser: HTML�t�@�C���擾(www.example.com/view/index.html)
    web�T�[�o-->>browser: JS�t�@�C���擾(www.example.com/js/api.js)
    browser-->>api: AJAX���N�G�X�g
    Note right of browser: SOP�ᔽ�ɂ�胊�N�G�X�g���s
```

## ����I���W�����f�̗�

�ȉ��̕\�́A�e�s�� URL �� http://store.company.com/dir/page.html �Ɠ����I���W���ł��邩���r�������̂ł��B

| URL                                        | ����     | ���R                           |
|--------------------------------------------|----------|-------------------------------|
| http://store.company.com/dir2/other.html   | ����I���W�� | �p�X�������قȂ�            |
| http://store.company.com/dir/inner/another.html | ����I���W�� | �p�X�������قȂ�            |
| https://store.company.com/page.html        | �s��v    | �v���g�R�����قȂ�             |
| http://store.company.com:81/dir/page.html  | �s��v    | �|�[�g�ԍ����قȂ� (http:// �͊���� 80 �ԃ|�[�g) |
| http://news.company.com/dir/page.html      | �s��v    | �z�X�g���قȂ�               |


## SOP�̖ړI
����I���W���|���V�[�iSOP�j�͎�Ɉȉ��̂悤�Ȑ��ݓI�ȍU����h���ړI�ō���܂���.

- �N���X�T�C�g�X�N���v�e�B���O�iXSS�j
XSS�́A�U���҂����ӂ̂���X�N���v�g���E�F�u�T�C�g�ɒ������A���̃X�N���v�g�����̃��[�U�[�̃u���E�U��Ŏ��s�����U���ł��BSOP�͂���I���W���̃X�N���v�g�����̃I���W���̃��\�[�X�ɃA�N�Z�X���邱�Ƃ𐧌����邱�ƂŁA���̎�̍U����h���������ʂ����܂��B

- �N���X�T�C�g���N�G�X�g�t�H�[�W�F���iCSRF�j
CSRF�́A�U���҂����[�U�[�̃u���E�U���g���āA���̃��[�U�[���F�؍ς݂̏�ԂŖK�₷��E�F�u�T�C�g�ɑ΂��ĈӐ}���Ȃ����N�G�X�g�𑗂点��U���ł��BSOP���Ȃ���΁A�U���҂͂���E�F�u�T�C�g���瑼�̃E�F�u�T�C�g�ւ̃��N�G�X�g���s���A���[�U�[�̃f�[�^�ɃA�N�Z�X�����葀�삵���肷��\��������܂��B

- �N���b�N�W���b�L���O
�N���b�N�W���b�L���O�́A�U���҂������ȃ��C���[�܂��̓t���[����p���āA���[�U�[�ɋC�Â��ꂸ�ɖ{���Ƃ͈قȂ郊���N��{�^�����N���b�N������U���ł��BSOP�ɂ��A����I���W���̃y�[�W���瑼�̃I���W���̃y�[�W�𑀍삷�邱�Ƃ���������܂��B

## SOP�̓K�p�ΏہE��K�p�Ώ�
Same Origin Policy���K�p�����͈̂ȉ��̏ꍇ�ł���B
- JavaScript �ł̔񓯊��ʐM�iAjax, ������ XMLHttpRequest �� Fetch API ���g�����ʐM�j
- CSS �ł� @font-face ���g���� Web �t�H���g�̓ǂݍ���
- WebGL �e�N�X�`���̓ǂݍ���
- canvas �� drawImage() ��p�����摜��r�f�I�t���[���̕`��
- �摜���� CSS �V�F�C�v�̐���

�K�p����Ȃ��͈̂ȉ��̏ꍇ�ł���
- img�^�O��src�����œǂݍ��񂾉摜
- link�^�O��href�����œǂݍ��� CSS
- script�^�O��src�����œǂݍ��� JavaScript
- form�^�O�� action �����Őݒ肵�����M�� URL
- video, audio �^�O��src�����œǂݍ��񂾃}���`���f�B�A�t�@�C��
- iframe, frame �^�O��src�����ł̕ʃT�C�g�R���e���c�̓ǂݍ���
X-Frame-Options �̐ݒ�ɂ���Ă͓ǂݍ��݂��u���b�N����܂�
JavaScript ��p���� iframe ���̃h�L�������g�ɃA�N�Z�X���邱�Ƃ͂ł��܂���

## Public API��SOP�Ή�

Google Maps API�̂悤��JavaScript���C�u�����́A���̓��������ɂ��ASOP�̐�������炵�A�u���E�U����T�[�o�[�ւ̃��N�G�X�g���s�����Ƃ��\�ɂȂ��Ă���B����̓��C�u�����̊J���҂��ACORS�̂悤�ȃ��J�j�Y���𗘗p����SOP�̐�������炷��������s���Ă��邩��ł���B

:::note info
Google Maps API�͔��s����API�L�[���g�p���āA���N�G�X�g���s�����߁AAPI�L�[��s�����p����Ȃ��悤�ɂ���K�v������B
��ʓI�ɂ�api key�ɑ΂���google map�̊Ǘ��R���\�[������A�N�Z�X���ireferer�j��ݒ肷�邱�ƂŁA�������s���^�p���邱�Ƃŕs�����p�̑Ή����s�����Ƃ��ł���B
�܂��AAPI�̗��p�͈͂̐����������邱�ƂŁAAPI�L�[���s���ɘR�k�����Ƃ��Ă��A���̃L�[�ŗ��p�ł���API�̎�ނ����񂳂�A��Q���ŏ����ɗ}���邱�Ƃ��ł���B
:::

�܂��A�t�����g�G���h����̃N���X�I���W�����N�G�X�g�������Ȃ��|���V�[��API�ɂ��Ă�CORS�T�|�[�g�����Ă��Ȃ����̂�����B
- Twitter API
- 

����ŁA��ʊJ���҂��A�u���E�U����A�N�Z�X����Web�T�[�o��API�T�[�o�𕪂��č\�z���AWeb�T�[�o����擾����javascript����API�T�[�o�ɑ΂���AJAX�ȂǂŔ񓯊����N�G�X�g����ۂɂ́ASOP�̖����l����K�v������B

SOP�΍�Ƃ��ẮA��ʓI�ɂ͈ȉ��̂悤�ȉ����@�����݂���B

- JSONP�iJSON with Padding�j�F
���̎�@�́Ascript�^�O���g����JSON�f�[�^�����[�h������@�ł��BJSONP��CORS�ɂ�鐧�������ł��܂����A�Z�L�����e�B��̃��X�N�����邽�߁A���݂ł͂��܂萄������Ă��܂���B
- CORS�w�b�_�[�F
�T�[�o�[���œK�؂�CORS�w�b�_�[��ݒ肷�邱�ƂŁA�قȂ�I���W������̃��N�G�X�g�������邱�Ƃ��ł��܂��BGoogle Maps API�̂悤�Ȉꕔ�̃T�[�r�X�ł́A�T�[�o�[���ł����̃w�b�_�[���K�؂ɐݒ肳��Ă��܂��B
- �v���L�V�T�[�o�[�F
���̎�@�́A�N���C�A���g�ƃT�[�o�[�̊Ԃɕʂ̃T�[�o�[�i�v���L�V�j�𗧂āA�v���L�V���N���C�A���g�̑���ɃT�[�o�[�ƒʐM���s�����@�ł��B����ɂ��A�u���E�U���F������"�I���W��"��ύX���邱�Ƃ��ł��ASOP������ł��܂��B
- �T�[�o�[�T�C�h�ʐM�F
���̎�@�́A�N���C�A���g�ł͂Ȃ��T�[�o�[����API���N�G�X�g���s�����@�ł��B����ɂ��A�u���E�U��SOP��CORS�̐�������S�ɉ�����邱�Ƃ��ł��܂��B

### JSONP�iJSON with Padding�j

- �@���[�U��web�y�[�W��v�����܂��B
- �A�u���E�U��web�T�[�o�ɑ΂���HTML�y�[�W�i��Findex.html�j��v�����܂��B
- �BWeb�T�[�o�[��index.html�����X�|���X���܂��B����index.html�ɂ́Aapi.example.com����f�[�^���擾���邽�߂�JavaScript�iscript�^�O���j���܂܂�Ă��܂��Bsrc�����ɂ�JSONP���g�����߂�URL�iapi.example.com?callback=myCallback�j���ݒ肳��Ă��܂��B
- �C�u���E�U�͂��̃X�N���v�g��ǂݍ��ނ��߂�API�T�[�o�[�ɑ΂���HTTP GET���N�G�X�g�𑗐M���܂��B���̃��N�G�X�g�ɂ�callback�p�����[�^�icallback=myCallback�j���܂܂�Ă��܂��B
- �DAPI�T�[�o�[�̓��X�|���X�Ƃ���JavaScript�R�[�h��Ԃ��܂��B����JavaScript�R�[�h��callback�֐��imyCallback�j���Ăяo���A���̈����Ɏ擾�����f�[�^��n���܂��B
�u���E�U�͂���JavaScript�R�[�h�����s���Acallback�֐����Ăяo����܂��B����callback�֐����Ńf�[�^�̏������s���܂��B

```mermaid
sequenceDiagram
    autonumber
    actor ���[�U
    participant browser as �u���E�U
    participant WebServer as Web Server (www.example.com)
    participant APIServer as API Server (api.example.com)
    ���[�U->>browser: URL���́ihttps://www.example.com�j
    browser->>WebServer: HTTP GET /index.html
    WebServer->>?browser: Response with index.html that includes script with src=api.example.com?callback=myCallback
    browser->>APIServer: HTTP GET /?callback=myCallback
    APIServer->>browser: Response with JavaScript: myCallback({ "key": "value" })
    browser->>browser: Execute JavaScript, call function myCallback
    Note over browser: The data is processed within the callback function.
```

### CORS�w�b�_�[

- �@���[�U��web�y�[�W��v�����܂��B
- �A�u���E�U��web�T�[�o�ɑ΂���HTML�y�[�W�i��Findex.html�j��v�����܂��B
- �BWeb�T�[�o�[��index.html�����X�|���X���܂��B����index.html�ɂ́Aapi.example.com����f�[�^���擾���邽�߂�JavaScript�iscript�^�O���j���܂܂�Ă��܂��B
- �C�u���E�U�͂���js��ǂݍ��ނ��߂�Web�T�[�o�ɑ΂���HTTP GET���N�G�X�g�𑗐M���܂��B
- �DWeb�T�[�o��api.js�����X�|���X���܂��B
- �E�u���E�U����Pre-flight���N�G�X�g��API�T�[�o�ɑ��M���܂�
  - Pre-flight���N�G�X�g�́A�E�F�u�A�v���P�[�V�������T�[�o�[�֓���̃^�C�v�̃N���X�I���W�����N�G�X�g�𑗐M����O�ɁA���̃��N�G�X�g�����S�ł��邱�Ƃ��m�F���邽�߂ɍs����B���̃��N�G�X�g��HTTP OPTIONS���\�b�h���g���čs���A��Ɉȉ��̂悤�ȏ󋵂Ŕ�������F
    - HTTP���\�b�h���V���v�����\�b�h�iGET�AHEAD�APOST�j�ȊO�̏ꍇ�B���Ƃ��΁APUT�ADELETE�ACONNECT�AOPTIONS�ATRACE�APATCH�Ȃǂ̃��\�b�h���g�p�����ꍇ�B
    - POST���N�G�X�g�ł����Ă��AContent-Type�w�b�_���ȉ��̒l�ȊO�̏ꍇ�F
      - application/x-www-form-urlencoded
      - multipart/form-data
      - text/plain
    - �C�ӂ�HTTP���\�b�h�̃��N�G�X�g�ŁA�J�X�^���w�b�_�i��FAPI�L�[���܂� X-Api-Key �w�b�_�Ȃǁj���g�p�����ꍇ
  - Pre-flight���N�G�X�g�ł͈ȉ��̃w�b�_���Z�b�g���AAPI���Ɏw�肵�����\�b�h�ƃw�b�_���󂯓���邩���m�F���܂��B
    - <b>Access-Control-Request-Method</b>: 
    ���̃w�b�_�[�̓v���t���C�g���N�G�X�g�Ɏg�p����A���ۂ̃��N�G�X�g�Ŏg�p����\���HTTP���\�b�h�iGET�APOST�APUT�Ȃǁj���T�[�o�[�ɓ`���܂��B����ɂ��A�T�[�o�[�͎w�肳�ꂽHTTP���\�b�h���󂯓���邩�ǂ����𔻒f���܂��B
    - <b>Access-Control-Request-Headers</b>: 
    ���̃w�b�_�[���v���t���C�g���N�G�X�g�Ɏg�p����܂����A������͎��ۂ̃��N�G�X�g�Ŏg�p����\��̃J�X�^��HTTP�w�b�_�[�̃��X�g���T�[�o�[�ɓ`���邽�߂̂��̂ł��B����ɂ��A�T�[�o�[�͂����̃w�b�_�[���󂯓���邩�ǂ����𔻒f���܂��B

�@�@
- �FAPI��CORS�w�b�_���Z�b�g���A���X�|���X��Ԃ��B
  - <b>Access-Control-Allow-Origin</b>:
   API�ւ̃N���X�I���W�����N�G�X�g��������I���W����ݒ肷��B

    - https://www.example.com������
     ~~~
     Access-Control-Allow-Origin: https://www.example.com
     ~~~

    - ���ׂẴI���W��������
     ~~~
     Access-Control-Allow-Origin: *
     ~~~

    - �����̃I���W��������
     ~~~
     �A�v���Ŏ������K�v
     ~~~

  - <b>Access-Control-Allow-Methods</b>:
   �N���X�I���W�����N�G�X�g�Ƃ��ċ�����HTTP���\�b�h���w��iGET, POST, PUT?�Ȃǁj
     - ����̃��\�b�h�݂̂�������(GET, POST)
     ~~~
     Access-Control-Allow-Methods: GET, POST
     ~~~
  - <b>Access-Control-Allow-Headers</b>:
  �N���X�I���W�����N�G�X�g�ŋ������HTTP�w�b�_�[���w�肵�܂��B�v���t���C�g���N�G�X�g�� Access-Control-Request-Headers �w�b�_�[�ŗv�����ꂽ�w�b�_�[���A���̃w�b�_�[�ŋ�����K�v������iContent-Type�Ȃǁj
     - �����̃w�b�_�[��������
     ~~~
     Access-Control-Allow-Headers: X-Requested-With, Content-Type, Accept, Origin, Authorization
     ~~~
  - <b>Access-Control-Expose-Headers</b>: 
  �N���X�I���W���̃��X�|���X�ň��S�ɘI�o�����邱�Ƃ��ł���w�b�_�[�̃z���C�g���X�g���u���E�U�ɓ`����B�f�t�H���g�ł́A�u���E�U�̓N���X�I���W���̃��X�|���X�ňꕔ�̊�{�I�ȃw�b�_�[�iCache-Control�AContent-Language�AContent-Type�AExpires�ALast-Modified�APragma�j������I�o����B
    - �����̃w�b�_�[�����J����
    ~~~
    Access-Control-Expose-Headers: X-My-Custom-Header, X-Another-Custom-Header
    ~~~
    ����6�̊�{�I�ȃ��X�|���X�w�b�_�[�́ACORS�Z�[�t���X�g�Ɋ܂܂�Ă��ď�Ɍ��J����܂�
    ~~~
    Cache-Control, Content-Language, Content-Length, Content-Type, Expires, Last-Modified, Pragma
    ~~~
  - <b>Access-Control-Max-Age</b>: 
  ����̃v���t���C�g���X�|���X���L���b�V���ł�����ԁi�b�P�ʁj���u���E�U�ɓ`���邱�Ƃ��ł���B����ɂ��A�����N���X�I���W�����N�G�X�g��p�ɂɍs���A�v���P�[�V�����́A�v���t���C�g���N�G�X�g�̃I�[�o�[�w�b�h���팸���邱�Ƃ��ł���B
    - 1���ԃL���b�V������
    ~~~
    Access-Control-Max-Age: 3600
    ~~~
  - <b>Access-Control-Allow-Credentials</b>: 
  �N���X�I���W�����N�G�X�g��Cookie��HTTP�F�؏����܂߂邱�Ƃ����ł���B���̃w�b�_�[��true�ɐݒ肳��Ă���ꍇ�A�t�����g�G���h�̃��N�G�X�g��withCredentials��true�ɐݒ肷��K�v������B
    - �F�؏���������
    ~~~
    Access-Control-Allow-Credentials: true
    ~~~
- �GAPI��GET���N�G�X�g�𑗐M����
- �HAPI�����X�|���X��Ԃ�

```mermaid
sequenceDiagram
    autonumber
    actor ���[�U
    participant browser as �u���E�U
    participant web�T�[�o as Web Server (www.example.com)
    participant api as API Server (api.example.com)
    ���[�U->>browser: URL���́ihttps://www.example.com�j
    browser->>web�T�[�o: HTTP GET /index.html
    web�T�[�o-->>browser: HTML�t�@�C���擾(www.example.com/index.html)
    browser->>web�T�[�o: HTTP GET /js/api.js
    web�T�[�o-->>browser: JS�t�@�C���擾(www.example.com/js/api.js)
     Note left of browser: CORS�w�b�_���Z�b�g<br/>Access-Control-Request-Method: GET, POST, PUT<br/>Access-Control-Allow-Methods: Content-Type, x-api-key
    browser->>api: Pre-flight���N�G�X�g�iOPTIONS���\�b�h�j
    api-->>browser: ���X�|���X
     Note right of api: CORS�w�b�_���Z�b�g<br/>Access-Control-Allow-Origin: https://www.example.com<br/>Access-Control-Allow-Methods: GET, POST, PUT<br/>Access-Control-Allow-Headers: Content-Type, x-api-key
     Note left of browser: Pre-flight�̃��X�|���X�ŁA<br>���N�G�X�g��������Ă��邽�߁A���N�G�X�g�\�B
     browser->>api: https://api.example.com/users�iGET���\�b�h, x-api-key�j
     api-->>browser: ���X�|���X
```

### �v���L�V�T�[�o

```mermaid
sequenceDiagram
    autonumber
    participant User as User
    participant Browser as Browser
    participant Proxy as Proxy Server
    participant API as API Server
    User->>Browser: Request resource
    Browser->>Proxy: Pre-flight request (OPTIONS)
    Proxy->>Browser: Response to pre-flight with CORS headers
    Note over Browser,Proxy: If the response is successful (i.e., Access-Control-Allow-Origin and other headers allow the request)
    Browser->>Proxy: Send actual request
    Proxy->>API: Forward actual request
    API->>Proxy: Response
    Proxy->>Browser: Response with CORS headers
```

### �T�[�o�[�T�C�h�ʐM

```mermaid
sequenceDiagram
    autonumber
    actor ���[�U
    participant browser as �u���E�U
    participant web�T�[�o as Web Server (www.example.com)
    participant api as API Server (api.example.com)
    ���[�U->>browser: URL���́ihttps://www.example.com�j
    browser->>web�T�[�o: HTTP GET /index.html
    web�T�[�o-->>browser: HTML�t�@�C���擾(www.example.com/index.html)
    browser->>web�T�[�o: HTTP GET /js/api.js
    web�T�[�o-->>browser: JS�t�@�C���擾(www.example.com/js/api.js)
     browser->>api: https://www.example.com/users�iGET���\�b�h, X-Api-Key�j
     api-->>browser: ���X�|���X
```

## API-Gateway�ł�CORS�̍\��

```mermaid
sequenceDiagram
    autonumber
    actor ���[�U
    participant browser as �u���E�U
    participant Amplify as Amplify (www.example.com)
    participant API Gateway as API Gateway (api.example.com)
    ���[�U->>browser: URL���́ihttps://www.example.com�j
    browser->>Amplify: HTTP GET /index.html
    Amplify-->>browser: HTML�t�@�C���擾(www.example.com/index.html)
    browser->>Amplify: HTTP GET /js/api.js
    Amplify-->>browser: JS�t�@�C���擾(www.example.com/js/api.js)
    browser->>API Gateway: https://www.example.com/users�iGET���\�b�h, X-Api-Key�j
    API Gateway-->>browser: ���X�|���X
```
