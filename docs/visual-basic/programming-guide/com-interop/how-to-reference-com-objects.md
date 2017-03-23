---
title: "방법: Visual Basic에서 COM 개체 참조 | Microsoft 문서"
ms.custom: 
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
- COM interop, referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: 13
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
ms.openlocfilehash: 97c132bcbd36ba7810acadb2aebddc5e84f0b44d
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>방법: Visual Basic에서 COM 개체 참조
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], COM 라이브러리에 대 한 interop 어셈블리의 생성이 필요한 형식 라이브러리가 있는 COM 개체에 대 한 참조를 추가 합니다. COM 개체의 멤버에 대 한 참조는 interop 어셈블리에 라우팅되고 실제 COM 개체에 전달 합니다. Interop 어셈블리를 COM 개체의 응답은 라우팅되고로 전달 하면 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 응용 프로그램입니다.  
  
 .NET 어셈블리에서 COM 개체에 대 한 형식 정보를 포함 하 여 interop 어셈블리를 사용 하지 않고 COM 개체를 참조할 수 있습니다. 형식 정보를 포함 하려면 설정의 `Embed Interop Types` 속성을 `True` COM 개체에 대 한 참조에 대 한 합니다. 명령줄 컴파일러를 사용 하 여 컴파일하는 사용 하 여는 `/link` COM 라이브러리를 참조 하는 옵션입니다. 자세한 내용은 참조 [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md)합니다.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]통합된 개발 환경 (IDE)에서 형식 라이브러리에 대 한 참조를 추가 하면 interop 어셈블리를 자동으로 만듭니다. 명령줄에서 작업을 하는 경우 interop 어셈블리를 수동으로 만들려고 Tlbimp 유틸리티를 사용할 수 있습니다.  
  
### <a name="to-add-references-to-com-objects"></a>COM 개체에 대 한 참조를 추가 하려면  
  
1.  에 **프로젝트** 메뉴 선택 **참조 추가** 클릭 하 고는 **COM** 대화 상자에서 탭 합니다.  
  
2.  COM 개체의 목록에서 사용 하려는 구성 요소를 선택 합니다.  
  
3.  Interop 어셈블리에 대 한 액세스를 간단 하 게 하려면 추가 `Imports` 문을 클래스나 모듈을 사용 하 여 COM 개체의 맨 위에 있습니다. 예를 들어, 다음 코드 예제에서는 네임 스페이스를 가져옵니다 `INKEDLib` 개체에서 참조 되는 `Microsoft InkEdit Control 1.0` 라이브러리입니다.  
  
     [!code-vb[VbVbalrInterop #&40;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a>Tlbimp를 사용 하 여 interop 어셈블리를 만들려면  
  
1.  아직 없는 검색 경로의 일부를 모르면 현재 위치한 디렉터리의 경우에 검색 경로에 Tlbimp의 위치를 추가 합니다.  
  
2.  다음 정보를 제공 하는 명령 프롬프트에서 Tlbimp를 호출 합니다.  
  
    -   형식 라이브러리를 포함 하는 DLL의 이름 및 위치  
  
    -   이름 및 네임 스페이스 정보를 배치할 위치  
  
    -   대상 interop 어셈블리의 이름 및 위치  
  
     다음 코드는 예제를 제공합니다.  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Tlbimp를 사용 하 여 등록 되지 않은 COM 개체에 대해서도 형식 라이브러리를 interop 어셈블리를 만들 수 있습니다. 그러나 interop 어셈블리에서 참조 하는 COM 개체는 사용할 수는 컴퓨터에 제대로 등록 되어야 합니다. Windows 운영 체제에 포함 된 Regsvr32 유틸리티를 사용 하 여 COM 개체를 등록할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tlbimp.exe (형식 라이브러리 가져오기)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)   
 [Tlbexp.exe (형식 라이브러리 내보내기)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)   
 [연습: COM 개체를 사용한 상속 구현](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [상호 운용성 문제 해결](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)   
 [Imports 문(.NET 네임스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
