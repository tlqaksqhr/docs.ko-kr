---
title: "Unable to emit assembly: &lt;error message&gt; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30145"
  - "bc30145"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30145"
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Unable to emit assembly: &lt;error message&gt;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러가 어셈블리 링커\(Al.exe, Alink라고도 함\)를 호출하여 매니페스트를 사용해 어셈블리를 생성합니다. 링커가 어셈블리 생성의 내보내기 단계에서 오류를 보고했습니다.  
  
 **오류 ID:** BC30145  
  
### 이 오류를 해결하려면  
  
1.  따옴표로 묶인 오류 메시지를 파악한 다음 [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/ko-kr/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) 항목에서 추가 설명과 권장 사항을 확인합니다.  
  
2.  [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md) 또는 [Sn.exe\(강력한 이름 도구\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)를 사용하여 어셈블리에 수동으로 서명해 봅니다.  
  
3.  오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.  
  
### 어셈블리에 수동으로 서명하려면  
  
1.  [Sn.exe\(강력한 이름 도구\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)를 사용하여 공개\/개인 키 쌍 파일을 만듭니다.  
  
     이 파일의 확장명은 .snk입니다.  
  
2.  프로젝트에서 오류를 생성하는 COM 참조를 삭제합니다.  
  
3.  Windows **시작** 메뉴에서 **프로그램**, **Microsoft Visual Studio 2008**, **Visual Studio Tools**를 차례로 가리킨 다음 **Visual Studio 2008 명령 프롬프트**를 클릭합니다.  
  
4.  어셈블리 래퍼를 배치할 디렉터리로 이동합니다.  
  
5.  다음 코드를 입력합니다.  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     입력할 수 있는 코드의 예는 다음과 같습니다.  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     경로나 파일에 공백이 있으면 큰따옴표\("\)를 사용합니다.  
  
6.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]에서 방금 만든 파일에 대한 .NET 어셈블리 참조를 추가합니다.  
  
## 참고 항목  
 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)   
 [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/ko-kr/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)   
 [Sn.exe\(강력한 이름 도구\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)   
 [방법: 공개\/개인 키 쌍 만들기](../Topic/How%20to:%20Create%20a%20Public-Private%20Key%20Pair.md)   
 [의견 보내기](/visual-studio/ide/talk-to-us)