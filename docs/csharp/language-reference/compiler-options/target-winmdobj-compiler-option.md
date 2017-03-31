---
title: "-target:winmdobj(C# 컴파일러 옵션) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7581ec18db0d2741452b47ad6200482b63c102be
ms.lasthandoff: 03/13/2017

---
# <a name="targetwinmdobj-c-compiler-options"></a>/target:winmdobj(C# 컴파일러 옵션)
**/target:winmdobj** 컴파일러 옵션을 사용하는 경우 컴파일러는 사용자가 Windows 런타임 이진(.winmd) 파일로 변환할 수 있는 중간 .winmdobj 파일을 만듭니다. 그런 다음 관리되는 언어 프로그램뿐만 아니라 JavaScript 및 C++ 프로그램에서도 .winmd 파일을 사용할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
/target:winmdobj  
```  
  
## <a name="remarks"></a>설명  
 **winmdobj** 설정이 컴파일러에 중간 모듈이 필요하다는 신호를 보냅니다. 이에 대한 응답으로 Visual Studio에서 C# 클래스 라이브러리를 .winmdobj 파일로 컴파일합니다. 그런 다음 <xref:Microsoft.Build.Tasks.WinMDExp> 내보내기 도구를 통해 .winmdobj 파일을 공급하여 Windows 메타데이터(.winmd) 파일을 만들 수 있습니다. .winmd 파일에는 원본 라이브러리의 코드와 JavaScript 또는 C++ 및 Windows 런타임에서 사용하는 WinMD 메타데이터가 모두 들어 있습니다.  
  
 **/target:winmdobj** 컴파일러 옵션을 사용하여 컴파일된 파일의 출력은 WimMDExp 내보내기 도구의 입력으로만 사용하도록 설계되었습니다. .winmdobj 파일 자체는 직접 참조되지 않습니다.  
  
 [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) 옵션을 사용하지 않으면 첫 번째 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다. [Main](../../../csharp/programming-guide/main-and-command-args/index.md) 메서드는 필요하지 않습니다.  
  
 명령 프롬프트에서 /target:winmdobj 옵션을 지정하면 Windows 프로그램을 만드는 데 다음 **/out** 또는 [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) 옵션까지의 모든 파일이 사용됩니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-ide-for-a-windows-store-app"></a>Windows 스토어 응용 프로그램용 Visual Studio IDE에서 이 컴파일러 옵션을 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.  
  
2.  **응용 프로그램** 탭을 선택합니다.  
  
3.  **출력 형식** 목록에서 **WinMD 파일**을 선택합니다.  
  
     **WinMD 파일** 옵션은 [!INCLUDE[win8_appname_long](../../../csharp/includes/win8_appname_long_md.md)] 앱 템플릿에만 사용할 수 있습니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 명령은 `filename.cs`를 중간 .winmdobj 파일로 컴파일합니다.  
  
```  
csc /target:winmdobj filename.cs  
```  
  
## <a name="see-also"></a>참고 항목  
 [/target(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)
