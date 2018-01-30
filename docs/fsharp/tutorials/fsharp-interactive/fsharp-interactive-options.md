---
title: "F# Interactive 옵션"
description: "F # Interactive에서 지 원하는 명령줄 옵션에 대 한 자세한 내용은 fsi.exe 합니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f9f3e39b-ce6c-41ff-991f-0625f46441ae
ms.openlocfilehash: a9b36a12aa9ffcfa26ea50d72d018a25f5f65243
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="f-interactive-options"></a>F# Interactive 옵션

> [!NOTE]
이 문서에서는 현재 Windows만을 위한 환경에 대해 설명합니다.  다시 작성될 예정입니다.

이 항목에서는 F # Interactive에서 지 원하는 명령줄 옵션 설명 `fsi.exe`합니다. F # Interactive F # 컴파일러와 같은 명령줄 옵션 중 상당수를 사용할 수 있지만 몇 가지 추가 옵션을 사용할 합니다.

## <a name="using-f-interactive-for-scripting"></a>사용 하 여 F # 대화형 스크립팅
F # Interactive, `fsi.exe`, 대화형으로 실행할 수 있습니다 또는 스크립트를 실행 하려면 명령줄에서 시작할 수 있습니다. 명령줄 구문

```
> fsi.exe [options] [ script-file [arguments] ]
```

F # 스크립트 파일의 파일 확장명은 `.fsx`합니다.

## <a name="table-of-f-interactive-options"></a>F # Interactive 옵션의 테이블
다음 표에서 F # Interactive에서 지 원하는 옵션을 요약 합니다. 명령줄에서 나 Visual Studio IDE를 통해 이러한 옵션을 설정할 수 있습니다. Visual Studio IDE에서 이러한 옵션을 설정 하려면 엽니다는 **도구** 메뉴 선택 **옵션...** , 다음 확장은 **F # 도구** 노드 선택한 **F # Interactive**합니다.

F # Interactive 옵션 인수에 목록이, 목록 요소는 세미콜론으로 구분 (`;`).

|옵션|설명|
|------|-----------|
|**--**|F # Interactive는 F # 프로그램 또는 목록을 사용 하 여 코드에서 액세스할 수 있는 스크립트에 명령줄 인수로 나머지 인수를 취급 하도록 지시 하는 데 사용 **fsi.CommandLineArgs**합니다.|
|**-확인**[**+**&#124; **-**]|와 동일는 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](../../language-reference/compiler-options.md)을 참조하세요.|
|**-코드 페이지:&lt;int&gt;**|와 동일는 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](../../language-reference/compiler-options.md)을 참조하세요.|
|**-crossoptimize**[**+**&#124; **-**]|크로스 모듈을 최적화를 사용 하지 않도록 설정 하거나 사용 합니다.|
|**-디버그**[**+**&#124; **-**]<br /><br />**-디버그:**[**전체**&#124; **pdbonly**]<br /><br />**-g**[**+**&#124; **-**]<br /><br />**-g:**[**전체**&#124; **pdbonly**]|와 동일는 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](../../language-reference/compiler-options.md)을 참조하세요.|
|**-정의:&lt;문자열&gt;**|와 동일는 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](../../language-reference/compiler-options.md)을 참조하세요.|
|**-exec**|F # interactive는 명령줄에 지정 된 스크립트 파일을 실행 하거나 파일을 로드 한 후 종료를 지시 합니다.|
|**-fullpaths**|와 동일는 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](../../language-reference/compiler-options.md)을 참조하세요.|
|**-gui**[**+**&#124; **-**]|Windows Forms 이벤트 루프를 사용 하지 않도록 설정 하거나 사용 합니다. 기본값은 사용입니다.|
|**-도움말**<br /><br />**-?**|명령줄 구문 및 각 옵션에 대 한 간략 한 설명을 표시 하는 데 사용 합니다.|
|**-lib:&lt;폴더 목록&gt;**<br /><br />**-I:&lt;폴더 목록&gt;**|와 동일는 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](../../language-reference/compiler-options.md)을 참조하세요.|
|**-로드:&lt;파일 이름&gt;**|시작 시 지정 된 소스 코드 컴파일하고 컴파일된 F # 구문 세션으로 로드 합니다. 대상 소스와 같은 스크립트 지시문을 포함 하는 경우 **#use** 또는 **#load**를 사용 해야 합니다 **-사용 하 여** 또는 **#use** 대신**-로드할** 또는 **#load**합니다.|
|**-mlcompatibility**|와 동일는 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](../../language-reference/compiler-options.md)을 참조하세요.|
|**-noframework**|와 동일는 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 참조 [컴파일러 옵션](../../language-reference/compiler-options.md)|
|**-nologo**|와 동일는 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](../../language-reference/compiler-options.md)을 참조하세요.|
|**-nowarn:&lt;경고 목록&gt;**|와 동일는 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](../../language-reference/compiler-options.md)을 참조하세요.|
|**-최적화**[**+**&#124; **-**]|와 동일는 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](../../language-reference/compiler-options.md)을 참조하세요.|
|**-quiet**|F # Interactive의 출력을 표시 하지 않는 **stdout** 스트림 합니다.|
|**-인용 디버그**|F # 따옴표로 묶인 리터럴을에서 파생 된 및 정의 반영 하는 식에 대 한 추가 정보를 디버깅 내보낼 수를 지정 합니다. 디버그 정보는 F # 식 트리 노드에 대 한 사용자 지정 특성으로 추가 됩니다. 참조 [코드 인용](../../language-reference/code-quotations.md) 및 [Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3)합니다.|
|**-readline**[**+**&#124; **-**]|대화형 모드에서 탭 완성 기능을 사용 하지 않도록 설정 하거나 사용 합니다.|
|**-참조:&lt;파일 이름&gt;**<br /><br />**-r:&lt;파일 이름&gt;**|와 동일는 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](../../language-reference/compiler-options.md)을 참조하세요.|
|**-tailcalls**[**+**&#124; **-**]|스택 프레임을 마무리 재귀 함수에 대 한 다시 사용할 수는 꼬리 IL 명령 사용 하지 않도록 설정 하거나 사용 합니다. 기본적으로 이 옵션은 사용하도록 설정됩니다.|
|**-사용:&lt;파일 이름&gt;**|인터프리터 초기 입력으로 시작할 때 지정된 된 파일을 사용 하도록 지시 합니다.|
|**-utf8output**|Fsc.exe 컴파일러 옵션와 동일 합니다. 자세한 내용은 [컴파일러 옵션](../../language-reference/compiler-options.md)을 참조하세요.|
|**-경고:&lt;경고 수준&gt;**|와 동일는 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](../../language-reference/compiler-options.md)을 참조하세요.|
|**-warnaserror**[**+**&#124; **-**]|와 동일는 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](../../language-reference/compiler-options.md)을 참조하세요.|
|**-warnaserror**[**+**&#124; **-** ]:**&lt;int 목록&gt;**|와 동일는 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](../../language-reference/compiler-options.md)을 참조하세요.|

## <a name="related-topics"></a>관련 항목

|제목|설명|
|-----|-----------|
|[컴파일러 옵션](../../language-reference/compiler-options.md)|F # 컴파일러를 사용할 수 있는 명령줄 옵션에 설명 **fsc.exe**합니다.|
