---
title: "-target:library(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e66e2edd86dc4a1302b23dab07226a5d56cb79b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="targetlibrary-c-compiler-options"></a>/target:library(C# 컴파일러 옵션)
**/target:library** 옵션을 사용하면 컴파일러가 실행 파일(EXE) 대신 DLL(동적 연결 라이브러리)을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```console  
/target:library  
```  
  
## <a name="remarks"></a>주의  
 DLL은 .dll 확장명으로 생성됩니다.  
  
 [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) 옵션을 사용하여 달리 지정되지 않은 경우 첫 번째 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다.  
  
 명령줄에서 지정된 경우, 다음 **/out** 또는 **/target: module** 옵션까지의 모든 파일이 .dll 파일을 만드는 데 사용됩니다.  
  
 .dll 파일을 빌드하는 경우에는 [Main](../../../csharp/programming-guide/main-and-command-args/index.md) 메서드가 필요하지 않습니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트 **속성** 페이지를 엽니다.  
  
2.  **응용 프로그램** 속성 페이지를 클릭합니다.  
  
3.  **출력 형식** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>를 참조하세요.  
  
## <a name="example"></a>예제  
 `in.cs`를 컴파일하고 `in.dll`을 만듭니다.  
  
```console  
csc /target:library in.cs  
```  
  
## <a name="see-also"></a>참고 항목  
 [/target (C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)
