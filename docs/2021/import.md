# import

다른 모듈에서 내보낸 바인딩을 가져올 때 사용한다.
가져오는 모듈은 "use strict"의 존재 유무와 상관없이 무조건 엄격 모드

** HTML 안에 작성한 스크립트에서는 import를 사용할 수 없다.

```js
import defaultExport from "module-name";
import * as name from "module-name";
import { export1 } from "module-name";
import { export1 as alias1 } from "module-name";
import { export1 , export2 } from "module-name";
import { foo , bar } from "module-name/path/to/specific/un-exported/file";
import { export1 , export2 as alias2 , [...] } from "module-name";
import defaultExport, { export1 [ , [...] ] } from "module-name";
import defaultExport, * as name from "module-name";
import "module-name";
var promise = import("module-name");
```
### defaultExport
모듈에서 가져온 기본 내보내기를 가리킬 이름.
### module-name
가져올 대상 모듈. 보통, 모듈을 담은 .js 파일로의 절대 또는 상대 경로
### name
가져온 대상에 접근할 때 일종의 이름공간으로 사용할, 모듈 객체의 이름.
### exportN
내보낸 대상 중 가져올 것의 이름.
### alias
가져온 유명 내보내기를 가리킬 이름.

> 참조: https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/import
