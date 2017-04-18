---
title: "방법: 클립보드에서 데이터 검색 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "클립보드, 데이터 검색"
  - "클립보드 데이터 붙여넣기"
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 클립보드에서 데이터 검색
<xref:System.Windows.Forms.Clipboard> 클래스는 Windows 운영 체제의 클립보드 기능과 상호 작용하는 데 사용할 수 있는 메서드를 제공합니다.  많은 응용 프로그램에서 클립보드를 데이터에 대한 임시 리포지토리로 사용합니다.  예를 들어, 워드 프로세서에서는 잘라내기\/붙여넣기 작업 중 클립보드를 사용합니다.  또한 클립보드는 한 응용 프로그램에서 다른 응용 프로그램으로 정보를 전송하는 데 유용합니다.  
  
 일부 응용 프로그램에서는 데이터를 더 많은 응용 프로그램에서 사용할 수 있도록 하기 위해 데이터를 여러 형식으로 클립보드에 저장합니다.  클립보드 형식은 형식을 식별하는 문자열입니다.  식별된 해당 형식을 사용하는 응용 프로그램에서는 클립보드에서 관련 데이터를 검색할 수 있습니다.  <xref:System.Windows.Forms.DataFormats> 클래스는 사용할 수 있는 미리 정의된 형식 이름을 제공합니다.  또한 고유한 형식 이름을 사용하거나 개체의 형식을 대신 사용할 수 있습니다.  데이터를 클립보드에 추가하는 방법에 대한 자세한 내용은 [방법: 클립보드에 데이터 추가](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)를 참조하십시오.  
  
 클립보드에 특정 형식의 데이터가 들어 있는지 확인하려면 `Contains`*Format* 메서드 중 하나 또는 <xref:System.Windows.Forms.Clipboard.GetData%2A> 메서드를 사용합니다.  클립보드의 데이터를 검색하려면 `Get`*Format* 메서드 중 하나 또는 <xref:System.Windows.Forms.Clipboard.GetData%2A> 메서드를 사용합니다.  이러한 메서드는 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서 새로 도입된 메서드입니다.  
  
 [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] 이전 버전을 사용하여 클립보드의 데이터에 액세스하려면 <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> 메서드를 사용하여 반환된 <xref:System.Windows.Forms.IDataObject>의 메서드를 호출합니다.  예를 들어, 반환된 개체에서 특정 형식을 사용할 수 있는지 확인하려면 <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> 메서드를 호출합니다.  
  
> [!NOTE]
>  모든 Windows 기반 응용 프로그램은 시스템 클립보드를 공유합니다.  따라서 다른 응용 프로그램으로 전환하면 클립보드 내용이 변경될 수 있습니다.  
>   
>  <xref:System.Windows.Forms.Clipboard> 클래스는 SAT\(단일 스레드 아파트\) 모드로 설정된 스레드에서만 사용할 수 있습니다.  이 클래스를 사용하려면 `Main` 메서드가 <xref:System.STAThreadAttribute> 특성으로 표시되어 있어야 합니다.  
  
### 클립보드에서 일반적인 단일 형식의 데이터를 검색하려면  
  
1.  <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A> 또는 <xref:System.Windows.Forms.Clipboard.GetText%2A> 메서드를 사용합니다.  필요에 따라 먼저 해당 `Contains`*Format* 메서드를 사용하여 데이터를 특정 형식으로 사용할 수 있는지 여부를 확인합니다.  이러한 메서드는 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서만 사용할 수 있습니다.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### 클립보드에서 사용자 지정 형식의 데이터를 검색하려면  
  
1.  <xref:System.Windows.Forms.Clipboard.GetData%2A> 메서드를 사용자 지정 형식 이름과 함께 사용합니다.  이 메서드는 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서만 사용할 수 있습니다.  
  
     또한 미리 정의된 형식 이름을 <xref:System.Windows.Forms.Clipboard.SetData%2A> 메서드와 함께 사용할 수 있습니다.  자세한 내용은 <xref:System.Windows.Forms.DataFormats>를 참조하십시오.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### 클립보드에서 여러 형식의 데이터를 검색하려면  
  
1.  <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> 메서드를 사용하십시오.  [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] 이전 버전에서 클립보드의 데이터를 검색하려면 이 메서드를 사용해야 합니다.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## 참고 항목  
 [끌어서 놓기 작업 및 클립보드 지원](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)   
 [방법: 클립보드에 데이터 추가](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)