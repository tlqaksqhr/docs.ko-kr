---
title: "/errorreport | Microsoft Docs"
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
  - "-errorreport compiler option [Visual Basic]"
  - "/errorreport compiler option [Visual Basic]"
  - "errorreport compiler option [Visual Basic]"
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# /errorreport
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러에서 내부 컴파일러 오류를 보고하는 방법을 지정합니다.  
  
## 구문  
  
```  
/errorreport:{ prompt | queue | send | none }  
```  
  
## 설명  
 이 옵션을 사용하면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] ICE\(내부 컴파일러 오류\)를 Microsoft의 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 팀에게 쉽게 보고할 수 있습니다.  기본적으로 컴파일러에서는 Microsoft에 아무런 정보도 보내지 않습니다.  그러나 내부 컴파일러 오류가 발생하는 경우 이 옵션을 사용하여 해당 오류를 Microsoft에 보고할 수 있습니다.  해당 정보는 Microsoft 엔지니어가 오류의 원인을 파악하는 데 도움이 되며 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]의 다음 릴리스 기능을 개선하는 데 도움이 될 수 있습니다.  
  
 사용자가 보고서를 보낼 수 있는지 여부는 컴퓨터 및 사용자 정책 권한에 따라 다릅니다.  
  
 다음 표에서는 `/errorreport` 옵션 효과를 요약하여 보여 줍니다.  
  
|||  
|-|-|  
|옵션|동작|  
|`prompt`|내부 컴파일러 오류가 발생한 경우 컴파일러에서 수집한 데이터를 정확하게 표시하는 대화 상자가 나타납니다.  오류 보고서에 중요한 정보가 포함되어 있는지 확인할 수 있으며 Microsoft에 해당 오류 보고서를 보낼지 여부를 결정할 수 있습니다.  사용자가 오류 보고서를 보내려는 경우 컴퓨터 및 사용자 정책 설정에서 허용하면 컴파일에서 해당 데이터를 Microsoft에 보냅니다.|  
|`queue`|오류 보고서가 큐에 저장됩니다.  관리자 권한으로 로그인하면 마지막으로 로그인한 이후 발생한 모든 오류를 보고할 수 있습니다. 오류 보고서를 전송할지 확인하는 메시지는 3일에 한 번 이상은 나타나지 않습니다.  `/errorreport` 옵션이 지정되지 않은 경우 기본 동작입니다.|  
|`send`|내부 컴파일러 오류가 발생한 경우 컴퓨터 및 사용자 정책 설정에서 허용하면 컴파일러에서 해당 데이터를 Microsoft에 보냅니다.<br /><br /> `/errorReport:send` 옵션은 오류를 Microsoft에 자동으로 보냅니다.  이 옵션은 레지스트리에 따라 달라집니다.  레지스트리에 적절한 값을 설정하는 방법은 [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command\-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695)를 참조하십시오.|  
|`none`|내부 컴파일러 오류가 발생해도 오류가 수집되거나 Microsoft로 전송되지 않습니다.|  
  
 컴파일러에서 보내는 데이터에는 오류 발생 시점의 스택 정보가 포함되며 여기에는 대개 일부 소스 코드도 포함됩니다.  `/errorreport`를 [\/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) 옵션과 함께 사용하면 소스 파일 전체가 전송됩니다.  
  
 이 옵션을 [\/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) 옵션과 함께 사용하면 Microsoft 엔지니어가 오류를 쉽게 재현할 수 있으므로 유용합니다.  
  
> [!NOTE]
>  `/errorreport` 옵션은 Visual Studio 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## 예제  
 다음 코드에서는 `T2.vb`를 컴파일하려고 시도하며 컴파일러에 내부 컴파일러 오류가 발생하는 경우 오류 보고서를 Microsoft에 보내라는 메시지가 나타납니다.  
  
```  
vbc /errorreport:prompt t2.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)