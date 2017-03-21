---
title: "주 / | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: 19
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
ms.openlocfilehash: dded7621845141896f353d69ab757010c825b975
ms.lasthandoff: 03/13/2017

---
# <a name="main"></a>/main
클래스 또는 포함 된 모듈 지정는 `Sub Main` 프로시저입니다.  
  
## <a name="syntax"></a>구문  
  
```  
/main:location  
```  
  
## <a name="arguments"></a>인수  
 `location`  
 필수 요소. 클래스 또는 포함 된 모듈의 정규화 된 `Sub Main` 프로그램이 시작 될 때 호출 되는 프로시저입니다. 형태로 제공 될 수 있습니다이 **/main:module** 또는 **/main:namespace.module**합니다.  
  
## <a name="remarks"></a>주의  
 실행 파일 또는 Windows 실행 프로그램을 만들 때이 옵션을 사용 합니다. 하는 경우는 **주/** 옵션을 생략 하면, 컴파일러는 유효한 공유에 대 한 검색 `Sub Main` 모든 공용 클래스와 모듈에 있습니다.  
  
 참조 [Visual Basic의 Main 프로시저](../../../visual-basic/programming-guide/program-structure/main-procedure.md) 에 대 한 다양 한 형태의 설명은 `Main` 프로시저입니다.  
  
 때 `location` 에서 상속 되는 클래스 <xref:System.Windows.Forms.Form>, 컴파일러는 기본 제공 `Main` 클래스가 없는 응용 프로그램을 시작 하는 프로시저 `Main` 절차.</xref:System.Windows.Forms.Form> 이렇게 하면 개발 환경에서 만든 명령줄에서 코드를 컴파일할 수 있습니다.  
  
 [!code-vb[VbVbalrCompiler #&16;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a>Visual Studio에서 /main을 설정 하려면 통합 개발 환경  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. 에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.  
  
     자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.  
  
2.  **응용 프로그램** 탭을 클릭합니다.  
  
3.  있는지 확인은 **응용 프로그램 프레임 워크 사용** 확인란을 선택 하지 않습니다.  
  
4.  값을 수정 된 **시작 개체** 상자입니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `T2.vb` 및 `T3.vb`로 지정 하 여 하는 `Sub Main` 프로시저에서 찾을 수는 `Test2` 클래스입니다.  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [NIB: Hello, World Visual Basic 버전](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)   
 [Visual Basic의 main 프로시저](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
