---
title: "How to: Reference COM Objects from Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "COM interop, referencing COM objects"
  - "referencing objects, COM objects from Visual Basic"
  - "objects [Visual Basic], referencing"
  - "COM objects, referencing"
  - "interop assemblies"
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# How to: Reference COM Objects from Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 형식 라이브러리가 있는 COM 개체에 대한 참조를 추가하려면 COM 라이브러리에 대한 interop 어셈블리를 만들어야 합니다.  COM 개체의 멤버에 대한 참조는 interop 어셈블리로 라우팅된 다음 실제 COM 개체로 전달되며,  COM 개체가 보내는 응답은 interop 어셈블리로 라우팅된 다음 해당 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 응용 프로그램으로 전달됩니다.  
  
 COM 개체에 대한 형식 정보를 .NET 어셈블리에 포함하여 interop 어셈블리를 사용하지 않고도 COM 개체를 참조할 수 있습니다.  형식 정보를 포함하려면 COM 개체에 대한 참조에 대해 `Embed Interop Types` 속성을 `True`로 설정합니다.  명령줄 컴파일러를 사용하여 컴파일하는 경우 `/link` 옵션을 사용하여 COM 라이브러리를 참조합니다.  자세한 내용은 [\/link](../../../visual-basic/reference/command-line-compiler/link.md)를 참조하십시오.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 IDE\(통합 개발 환경\)에서 형식 라이브러리에 대한 참조를 추가할 때 자동으로 interop 어셈블리를 만듭니다.  명령줄에서 작업하는 경우 Tlbimp 유틸리티를 사용하여 수동으로 interop 어셈블리를 만들 수 있습니다.  
  
### COM 개체에 대한 참조를 추가하려면  
  
1.  **프로젝트** 메뉴에서 **참조 추가**를 선택한 다음 대화 상자의 **COM** 탭을 클릭합니다.  
  
2.  COM 개체 목록에서 사용할 구성 요소를 선택합니다.  
  
3.  Interop 어셈블리에 대한 액세스를 단순화하려면 COM 개체를 사용할 클래스나 모듈 맨 위에 `Imports` 문을 추가합니다.  예를 들어 다음 코드 예제에서는 `Microsoft InkEdit Control 1.0` 라이브러리에서 참조되는 개체를 위해 `INKEDLib` 네임스페이스를 가져옵니다.  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### Tlbimp를 사용하여 interop 어셈블리를 만들려면  
  
1.  Tlbimp의 위치가 아직 검색 경로에 포함되어 있지 않고 현재 디렉터리가 Tlbimp가 있는 디렉터리가 아닌 경우 Tlbimp의 위치를 검색 경로에 추가합니다.  
  
2.  명령 프롬프트에서 다음과 같은 정보를 제공하여 Tlbimp를 호출합니다.  
  
    -   형식 라이브러리를 포함하는 DLL의 이름과 위치  
  
    -   정보가 있어야 할 네임스페이스의 이름과 위치  
  
    -   대상 interop 어셈블리의 이름과 위치  
  
     코드 예제는 다음과 같습니다.  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Tlbimp를 사용하여 형식 라이브러리에 대한 interop 어셈블리를 만들 수 있습니다. 이는 등록되지 않은 COM 개체에 대해서도 마찬가지입니다.  그러나 interop 어셈블리에서 참조되는 COM 개체는 해당 개체를 사용할 컴퓨터에 올바르게 등록되어 있어야 합니다.  COM 개체는 Windows 운영 체제에 포함된 Regsvr32 유틸리티를 사용하여 등록할 수 있습니다.  
  
## 참고 항목  
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tlbimp.exe\(형식 라이브러리 가져오기\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)   
 [Tlbexp.exe\(형식 라이브러리 내보내기\)](../Topic/Tlbexp.exe%20\(Type%20Library%20Exporter\).md)   
 [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)   
 [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)