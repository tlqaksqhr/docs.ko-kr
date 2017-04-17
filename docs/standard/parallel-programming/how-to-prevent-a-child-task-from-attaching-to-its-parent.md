---
title: "How to: Prevent a Child Task from Attaching to its Parent | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "tasks, preventing attachments"
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# How to: Prevent a Child Task from Attaching to its Parent
이 문서에서는 자식 작업이 부모 작업으로 연결하는 것을 방지하는 방법을 보여 줍니다.  자식 작업을 부모에 연결하는 것을 방지하는 것은 제3자에 의해 작성되거나 작업을 사용하는 구성 요소를 호출하는 경우 유용 합니다.  예를 들어, <xref:System.Threading.Tasks.TaskCreationOptions?displayProperty=fullName> 옵션을 사용하여 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601> 개체를 생성하는 제3의 요소는 장기 실행 또는 처리 되지 않은 예외를 throw 하면 코드에 문제를 발생시킬 수 있습니다.  
  
## 예제  
 다음 예제에서는 자식 작업이 부모에 연결하는 것에 대한 방지의 효과를 기본 옵션으로 사용한 결과들을 비교 합니다.  예제에서는 <xref:System.Threading.Tasks.Task> 개체를 사용하는 제3의 라이브러리를 호출하는 <xref:System.Threading.Tasks.Task> 개체를 생성합니다.  제3의 라이브러리는 <xref:System.Threading.Tasks.TaskCreationOptions> 옵션을 사용하여 <xref:System.Threading.Tasks.Task> 개체를 생성합니다.  응용 프로그램은 <xref:System.Threading.Tasks.TaskCreationOptions?displayProperty=fullName> 옵션을 사용하여 부모 작업을 만듭니다.  이 옵션을 런타임에 자식 작업의 <xref:System.Threading.Tasks.TaskCreationOptions> 사양을 제거하도록 지시합니다.  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 자식 작업이 모두 완료될 때까지 부모 작업은 완료되지 않으므로 오래 실행되는 자식 작업은 전체 응용 프로그램의 성능을 떨어뜨릴 수 있습니다.  이 예제에서 응용 프로그램은 기본 옵션을 사용하여 부모 작업을 생성해야 할 때, 자식 작업은 부모 작업이 완료되기 전에 완료되야 합니다.  응용 프로그램에서 <xref:System.Threading.Tasks.TaskCreationOptions?displayProperty=fullName> 옵션을 사용하는 경우, 자식은 부모에 연결되어 있지 않습니다.  따라서 응용 프로그램은 하위 작업이 끝나기를 기다려야 하기 전, 그리고 부모 작업이 완료 된 후 추가 작업을 수행 수 있습니다.  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트에 붙여넣거나 `DenyChildAttach.cs` \([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 의 `DenyChildAttach.vb`\) 파일에 붙여넣은 다음 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe DenyChildAttach.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe DenyChildAttach.vb**  
  
## 강력한 프로그래밍  
  
## 참고 항목  
 [Task Parallelism](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)