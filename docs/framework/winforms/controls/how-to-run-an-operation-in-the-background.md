---
title: "방법: 백그라운드에서 작업 실행 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "백그라운드 작업"
  - "백그라운드 작업"
  - "백그라운드 스레드"
  - "BackgroundWorker 클래스, 예제"
  - "폼, 백그라운드 작업"
  - "폼, 다중 스레딩"
  - "스레딩[Windows Forms], 백그라운드 작업"
ms.assetid: 5b56e2aa-dc05-444f-930c-2d7b23f9ad5b
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 백그라운드에서 작업 실행
완료하는 데 오랜 시간이 걸리는 작업이 있으며 사용자 인터페이스에서 지연이 발생되지 않게 하려는 경우 <xref:System.ComponentModel.BackgroundWorker> 클래스를 사용하여 다른 스레드에서 작업을 실행할 수 있습니다.  
  
 다음 코드 예제에서는 시간이 많이 걸리는 작업을 백그라운드에서 실행하는 방법을 보여 줍니다.  폼에는 **Start** 및 **Cancel** 단추가 있습니다.  비동기 작업을 실행하려면 **Start** 단추를 클릭합니다.  비동기 작업 실행을 중지하려면 **Cancel** 단추를 클릭합니다.  각 작업의 결과가 <xref:System.Windows.Forms.MessageBox>에 표시됩니다.  
  
 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서는 이 작업이 광범위하게 지원됩니다.  
  
 [연습: 백그라운드에서 작업 실행](http://msdn.microsoft.com/library/ms233672\(v=vs.110\))을 참조하세요.  
  
## 예제  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 명령줄에서 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]용으로 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) 또는 [csc.exe를 사용한 명령줄 빌드](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## 참고 항목  
 <xref:System.ComponentModel.BackgroundWorker>   
 <xref:System.ComponentModel.DoWorkEventArgs>   
 [방법: 백그라운드 작업을 사용하는 폼 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [BackgroundWorker 구성 요소](../../../../docs/framework/winforms/controls/backgroundworker-component.md)