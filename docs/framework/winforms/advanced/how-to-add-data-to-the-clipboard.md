---
title: "방법: 클립보드에 데이터 추가 | Microsoft Docs"
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
  - "클립보드, 데이터 복사"
  - "데이터[Windows Forms], 클립보드에 복사"
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 클립보드에 데이터 추가
<xref:System.Windows.Forms.Clipboard> 클래스는 Windows 운영 체제의 클립보드 기능과 상호 작용하는 데 사용할 수 있는 메서드를 제공합니다.  많은 응용 프로그램에서 클립보드를 데이터에 대한 임시 리포지토리로 사용합니다.  예를 들어, 워드 프로세서에서는 잘라내기\/붙여넣기 작업 중 클립보드를 사용합니다.  또한 클립보드는 한 응용 프로그램에서 다른 응용 프로그램으로 데이터를 전송하는 데 유용합니다.  
  
 데이터를 클립보드에 추가할 때 데이터 형식을 나타낼 수 있습니다. 이렇게 하면 다른 응용 프로그램에서 해당 형식을 사용할 수 있을 경우에만 해당 데이터가 인식됩니다.  또한 데이터를 다양한 형식으로 클립보드에 추가하여 데이터를 사용할 수 있는 다른 응용 프로그램의 수를 늘릴 수 있습니다.  
  
 클립보드 형식은 해당 형식을 사용하는 응용 프로그램에서 연결된 데이터를 검색할 수 있도록 형식을 식별하는 문자열입니다.  <xref:System.Windows.Forms.DataFormats> 클래스는 사용할 수 있는 미리 정의된 형식 이름을 제공합니다.  또한 고유한 형식 이름을 사용하거나 개체의 형식을 대신 사용할 수 있습니다.  
  
 하나 이상의 형식으로 데이터를 클립보드에 추가하려면 <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> 메서드를 사용합니다.  이 메서드에는 아무 개체나 전달할 수 있지만 데이터를 여러 형식으로 추가하려면 먼저 여러 형식에 대해 작동하도록 설계된 별도의 개체에 데이터를 추가해야 합니다.  일반적으로는 데이터를 <xref:System.Windows.Forms.DataObject>에 추가하지만 <xref:System.Windows.Forms.IDataObject> 인터페이스를 구현하는 형식을 사용할 수도 있습니다.  
  
 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서는 기본 클립보드 작업을 쉽게 수행할 수 있도록 설계된 새 메서드를 사용하여 데이터를 클립보드에 직접 추가할 수 있습니다.  이러한 메서드는 텍스트 같은 일반적인 단일 형식의 데이터를 처리하는 경우에만 사용합니다.  
  
> [!NOTE]
>  모든 Windows 기반 응용 프로그램은 클립보드를 공유합니다.  따라서 다른 응용 프로그램으로 전환하면 클립보드 내용이 변경될 수 있습니다.  
>   
>  <xref:System.Windows.Forms.Clipboard> 클래스는 SAT\(단일 스레드 아파트\) 모드로 설정된 스레드에서만 사용할 수 있습니다.  이 클래스를 사용하려면 `Main` 메서드가 <xref:System.STAThreadAttribute> 특성으로 표시되어 있어야 합니다.  
>   
>  개체는 serialize 가능해야 클립보드에 넣을 수 있습니다.  형식을 serialize 가능하게 만들려면 형식을 <xref:System.SerializableAttribute> 특성으로 표시합니다.  Clipboard 메서드에 serialize할 수 없는 개체를 전달하면 메서드가 예외를 throw하지 않고 실패합니다.  Serialization에 대한 자세한 내용은 <xref:System.Runtime.Serialization>을 참조하십시오.  
  
### 일반적인 단일 형식으로 클립보드에 데이터를 추가하려면  
  
1.  <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A> 또는 <xref:System.Windows.Forms.Clipboard.SetText%2A> 메서드를 사용합니다.  이러한 메서드는 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서만 사용할 수 있습니다.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### 사용자 지정 형식으로 클립보드에 데이터를 추가하려면  
  
1.  <xref:System.Windows.Forms.Clipboard.SetData%2A> 메서드를 사용자 지정 형식 이름과 함께 사용합니다.  이 메서드는 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서만 사용할 수 있습니다.  
  
     또한 미리 정의된 형식 이름을 <xref:System.Windows.Forms.Clipboard.SetData%2A> 메서드와 함께 사용할 수 있습니다.  자세한 내용은 <xref:System.Windows.Forms.DataFormats>를 참조하십시오.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### 여러 형식으로 클립보드에 데이터를 추가하려면  
  
1.  <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> 메서드를 사용하여 데이터가 포함된 <xref:System.Windows.Forms.DataObject>를 전달합니다.  [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] 이전 버전에서 클립보드에 데이터를 추가하려면 이 메서드를 사용해야 합니다.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## 참고 항목  
 [끌어서 놓기 작업 및 클립보드 지원](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)   
 [방법: 클립보드에서 데이터 검색](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)