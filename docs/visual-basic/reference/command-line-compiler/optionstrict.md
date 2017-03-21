---
title: "/optionstrict | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optionstrict
dev_langs:
- VB
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0394d9c1f4c082271316829ef1d226bd97d136c9
ms.lasthandoff: 03/13/2017

---
# <a name="optionstrict"></a>/optionstrict
암시적 형식 변환을 제한 하는 엄격한 형식 의미 체계를 적용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/optionstrict[+ | -]  
/optionstrict[:custom]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 선택적 요소. `/optionstrict+` 옵션 암시적 형식 변환을 제한 합니다. 이 옵션의 기본값은 `/optionstrict-`합니다. `/optionstrict+` 옵션은 동일 `/optionstrict`합니다. 관대 한 형식 의미 체계를 모두 사용할 수 있습니다.  
  
 `custom`  
 필수 요소. 엄격한 언어 의미 체계를 준수하지 않을 경우 경고합니다.  
  
## <a name="remarks"></a>주의  
 때 `/optionstrict+` 사실에 확장 유형 변환만 암시적으로 만들 수 있습니다. 암시적 형식 변환의 경우 할당 하는 등 축소는 `Decimal` integer 형식 개체를 object 형식, 오류로 보고 됩니다.  
  
 축소 하는 암시적 형식 변환에 대 한 경고를 생성 하려면 사용 `/optionstrict:custom`합니다. 사용 하 여 `/nowarn:numberlist` 특정 경고를 무시 하 고 `/warnaserror:numberlist` 특정 경고를 오류로 처리 하도록 합니다.  
  
### <a name="to-set-optionstrict-in-the-visual-studio-ide"></a>Visual Studio IDE에서 /optionstrict을 설정 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. 에 **프로젝트** 메뉴를 클릭 하 여 **속성입니다.** 자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.  
  
2.  클릭 하 고 **컴파일** 탭 합니다.  
  
3.  값을 수정 된 **Option Strict** 상자입니다.  
  
### <a name="to-set-optionstrict-programmatically"></a>/Optionstrict을 프로그래밍 방식으로 설정 하려면  
  
-   참조 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `Test.vb` 엄격한 형식 의미 체계를 사용 합니다.  
  
```  
vbc /optionstrict+ test.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)   
 [/warnaserror(Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [옵션 대화 상자, 프로젝트, Visual Basic 기본값](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
