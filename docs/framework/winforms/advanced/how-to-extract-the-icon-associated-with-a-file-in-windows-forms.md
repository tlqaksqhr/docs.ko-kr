---
title: "방법: Windows Forms에서 파일과 연결된 아이콘 추출"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a5153f6389c4477a18c647d7cdaf7b49b43bb7ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a>방법: Windows Forms에서 파일과 연결된 아이콘 추출
많은 파일을 시각적 연결된 된 파일 형식으로 제공 하는 아이콘 포함 되어 있습니다. 예를 들어 Microsoft Word 문서 Word 문서를 식별 하는 아이콘을 포함 합니다. Table 컨트롤 또는 목록 컨트롤에 파일을 표시할 때 각 파일 이름 옆에 있는 파일 형식을 나타내는 아이콘을 표시 하는 것이 좋습니다. 사용 하 여이 작업을 쉽게 수행할 수 있습니다는 <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> 메서드.  
  
## <a name="example"></a>예  
 파일과 연결 된 아이콘 추출 하 고 파일 이름 및 연결 된 아이콘을 표시 하는 방법은 다음 코드 예제는 <xref:System.Windows.Forms.ListView> 제어 합니다.  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제를 컴파일하려면:  
  
-   Windows Form 및 호출에 앞의 코드를 붙여는 `ExtractAssociatedIconExample` 폼의 생성자에서 메서드 또는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리 메서드.  
  
     양식에 가져옵니다 있는지 확인 해야 합니다는 <xref:System.IO> 네임 스페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [ListView 컨트롤](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
