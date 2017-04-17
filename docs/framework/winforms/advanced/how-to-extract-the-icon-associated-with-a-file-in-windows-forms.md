---
title: "방법: Windows Forms에서 파일과 연결된 아이콘 추출 | Microsoft Docs"
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
  - "ListView 컨트롤에 파일 이름 및 해당 파일 형식 아이콘 나타내기[Windows Forms]"
  - "파일 형식과 연결된 아이콘 추출[Windows Forms]"
  - "파일 이름 확장 아이콘[Windows Forms], ListView에 표시"
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: Windows Forms에서 파일과 연결된 아이콘 추출
많은 파일에는 연관된 파일 형식의 시각적 표현을 제공하는 아이콘이 포함되어 있습니다.  예를 들어, Microsoft Word 문서에는 해당 문서가 Word 문서임을 알게 해 주는 아이콘이 있습니다.  목록 컨트롤이나 테이블 컨트롤에 파일을 표시할 때 각 파일 이름 옆에 파일 형식을 나타내는 아이콘을 표시할 수 있습니다.  <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> 메서드를 사용하면 이 작업을 쉽게 수행할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 파일과 연관된 아이콘을 추출하고 <xref:System.Windows.Forms.ListView> 컨트롤에 파일 이름과 관련 아이콘을 표시하는 방법을 보여 줍니다.  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## 코드 컴파일  
 예제를 컴파일하려면  
  
-   위의 코드를 Windows Form에 붙여넣고 폼의 생성자나 <xref:System.Windows.Forms.Form.Load> 이벤트 처리 메서드에서 `ExtractAssociatedIconExample` 메서드를 호출합니다.  
  
     폼에서 <xref:System.IO> 네임스페이스를 가져오는지 확인해야 합니다.  
  
## 참고 항목  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [ListView 컨트롤](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)