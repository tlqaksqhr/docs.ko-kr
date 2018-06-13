---
title: -nowin32manifest(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /nowin32manifest
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
ms.openlocfilehash: a07ead99ddd4e230fff8d1452ef81171ed849b29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33214934"
---
# <a name="-nowin32manifest-c-compiler-options"></a>-nowin32manifest(C# 컴파일러 옵션)
**-nowin32manifest** 옵션을 사용하면 실행 파일에 응용 프로그램 매니페스트를 포함하지 않도록 컴파일러에 지시할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a>설명  
 이 옵션을 사용하는 경우 Win32 리소스 파일에서 또는 이후 빌드 단계 중에 응용 프로그램 매니페스트를 제공하지 않으면 Windows Vista에서 응용 프로그램에 가상화가 적용됩니다.  
  
 Visual Studio의 **응용 프로그램 속성** 페이지에 있는 **매니페스트** 드롭다운 목록에서 **매니페스트 없이 응용 프로그램 만들기** 옵션을 선택하여 이 옵션을 설정합니다. 자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지(C#)](/visualstudio/ide/reference/application-page-project-designer-csharp)를 참조하세요.  
  
 매니페스트 생성에 대한 자세한 내용은 [-win32manifest(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)  
 [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)
