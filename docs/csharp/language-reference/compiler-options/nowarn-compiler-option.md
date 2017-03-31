---
title: "-nowarn(C# 컴파일러 옵션) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /nowarn
dev_langs:
- CSharp
helpviewer_keywords:
- nowarn compiler option [C#]
- /nowarn compiler option [C#]
- -nowarn compiler option [C#]
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 34152b6e7247ac112bcc9c725402b8c9a5d631ed
ms.lasthandoff: 03/13/2017

---
# <a name="nowarn-c-compiler-options"></a>/nowarn(C# 컴파일러 옵션)
**/nowarn** 옵션을 사용하면 컴파일러에서 하나 이상의 경고를 표시하지 않을 수 있습니다. 여러 경고 번호를 쉼표로 구분합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/nowarn:number1[,number2,...]  
```  
  
## <a name="arguments"></a>인수  
 `number1`, `number2`  
 컴파일러에서 표시하지 않으려는 경고 번호입니다.  
  
## <a name="remarks"></a>주의  
 경고 식별자의 숫자 부분만 지정해야 합니다. 예를 들어 CS0028을 표시하지 않으려면 `/nowarn:28`을 지정할 수 있습니다.  
  
 컴파일러는 이전 릴리스에서 유효했지만 현재 컴파일러에서 제거된, `/nowarn`에 전달된 경고 번호를 자동으로 무시합니다. 예를 들어 CS0679는 Visual Studio.NET 2002의 컴파일러에서 유효했지만 이후에 제거되었습니다.  
  
 다음 경고는 `/nowarn` 옵션으로 표시되지 않도록 설정할 수 없습니다.  
  
-   컴파일러 경고(수준 1) CS2002  
  
-   컴파일러 경고(수준 1) CS2023  
  
-   컴파일러 경고(수준 1) CS2029  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다. 자세한 내용은 [프로젝트 디자이너, 빌드 페이지(C#)](https://docs.microsoft.com/visualstudio/ide/reference/build-page-project-designer-csharp)를 참조하세요.  
  
2.  **빌드** 속성 페이지를 클릭합니다.  
  
3.  **경고 표시 안 함** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)   
 [NIB 방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [C# 컴파일러 오류](../../../csharp/language-reference/compiler-messages/index.md)
