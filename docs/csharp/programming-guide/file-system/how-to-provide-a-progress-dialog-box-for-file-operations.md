---
title: "방법: 파일 작업에 대한 진행률 대화 상자 제공(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "진행률 대화 상자[C#]"
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: 파일 작업에 대한 진행률 대화 상자 제공(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic?displayProperty=fullName> 네임스페이스에서 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> 메서드를 사용하면 Windows에서 파일 작업에 대한 진행률을 표시하는 표준 대화 상자를 제공할 수 있습니다.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Visual Studio에서 참조를 추가하려면  
  
1.  메뉴 모음에서 **프로젝트**, **참조 추가**를 선택합니다.  
  
     **참조 관리자** 대화 상자가 나타납니다.  
  
2.  **어셈블리** 영역에서 **프레임워크**가 아직 선택되어 있지 않으면 프레임워크를 선택합니다.  
  
3.  이름 목록에서, **Microsoft.VisualBasic** 확인란을 선택하고 나서, **확인** 단추를 선택하면 대화 상자가 닫힙니다.  
  
## 예제  
 다음 코드에서는 `sourcePath`에서 지정하는 디렉터리를 `destinationPath`에서 지정하는 디렉터리로 복사합니다.  이 코드에서는 또한 작업이 끝날 때까지 남은 추정 시간을 보여 주는 표준 대화 상자도 제공합니다.  
  
 [!code-cs[csFilesandFolders#11](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-provide-a-progress-dialog-box-for-file-operations_1.cs)]  
  
## 참고 항목  
 [파일 시스템 및 레지스트리](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)