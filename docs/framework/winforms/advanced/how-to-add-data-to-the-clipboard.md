---
title: "방법: 클립보드에 데이터 추가"
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
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 452dfc5a9645e8f43ab583099deec60faa2d1b4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-data-to-the-clipboard"></a>방법: 클립보드에 데이터 추가
<xref:System.Windows.Forms.Clipboard> 클래스 Windows 운영 체제 클립보드 기능와 상호 작용 하는 데 사용할 수 있는 메서드를 제공 합니다. 많은 응용 프로그램 데이터에 대 한 임시 저장소로 클립보드를 사용 합니다. 예를 들어 워드 프로세서 잘라내기 / 붙여넣기 작업 중 클립보드를 사용합니다. 클립보드에서 응용 프로그램 간에 데이터를 전송 하는 데 도움이 됩니다.  
  
 클립보드에 데이터를 추가 하면 해당 형식을 사용할 수 있는 경우 다른 응용 프로그램 데이터를 인식할 수 있도록 데이터 형식을 나타낼 수 있습니다. 또한 잠재적으로 데이터를 사용할 수 있는 다른 응용 프로그램의 수를 늘리기 위해 다양 한 형식으로 클립보드에 데이터를 추가할 수 있습니다.  
  
 클립보드 형식을 해당 형식을 사용 하는 응용 프로그램 관련된 데이터를 검색할 수 있도록 형식을 식별 하는 문자열입니다. <xref:System.Windows.Forms.DataFormats> 클래스 사용에 대 한 미리 정의 된 형식 이름을 제공 합니다. 직접 형식 이름을 사용 하거나 해당 형식으로 개체의 형식을 사용할 수도 있습니다.  
  
 하나 이상의 형식으로 클립보드에 데이터를 추가 하려면 사용 된 <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> 메서드. 이 메서드를 모든 개체를 전달할 수 있습니다 하지만 여러 형식의 데이터를 추가 하려면 먼저 추가 해야 데이터를 별도 개체로 여러 서식을 함께 사용 하도록 합니다. 사용자 데이터를 추가 합니다는 일반적으로 <xref:System.Windows.Forms.DataObject>, 구현 하는 모든 형식을 사용할 수 있습니다 하지만 <xref:System.Windows.Forms.IDataObject> 인터페이스.  
  
 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], 기본 클립보드 작업을 쉽게 수행할 수 있도록 설계 된 새 메서드를 사용 하 여 데이터를 클립보드에 직접 추가할 수 있습니다. 일반적인 단일 형식의 예: 텍스트에서 데이터로 작업 하는 경우 이러한 메서드를 사용 합니다.  
  
> [!NOTE]
>  모든 Windows 기반 응용 프로그램은 클립보드를 공유 합니다. 따라서 내용이 변경 될 수 다른 응용 프로그램으로 전환 합니다.  
>   
>  <xref:System.Windows.Forms.Clipboard> 클래스는 단일 스레드 아파트 (STA) 모드로 설정에 사용할 수 있습니다. 이 클래스를 사용 하려면 프로그램 `Main` 표시 된 메서드가 <xref:System.STAThreadAttribute> 특성입니다.  
>   
>  개체를 클립보드에 저장 하도록 직렬화 할 수 있어야 합니다. 사용 하 여 표시 형식을 직렬화 할 수 있도록 하는 <xref:System.SerializableAttribute> 특성입니다. 클립보드 메서드에 순차 불가능 한 개체를 전달 하는 경우에 메서드가 예외를 throw 하지 않고 실패 합니다. serialization에 대한 자세한 내용은 <xref:System.Runtime.Serialization>을 참조하세요.  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a>단일의 공통 형식으로 클립보드에 데이터를 추가 하려면  
  
1.  사용 하 여는 <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, 또는 <xref:System.Windows.Forms.Clipboard.SetText%2A> 메서드. 이러한 메서드는 에서만 사용할 수 있습니다. [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]합니다.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a>사용자 지정 형식으로 클립보드에 데이터를 추가 하려면  
  
1.  사용 된 <xref:System.Windows.Forms.Clipboard.SetData%2A> 메서드에 사용자 지정 형식 이름 합니다. 이 메서드는 영어로 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]합니다.  
  
     미리 정의 된 형식 이름으로 사용할 수도 있습니다는 <xref:System.Windows.Forms.Clipboard.SetData%2A> 메서드. 자세한 내용은 <xref:System.Windows.Forms.DataFormats>을 참조하세요.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a>여러 형식으로 클립보드에 데이터를 추가 하려면  
  
1.  사용 하 여는 <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> 메서드와 전달은 <xref:System.Windows.Forms.DataObject> 데이터가 포함 된 합니다. 버전에서 클립보드에 데이터를 추가 하려면이 메서드를 사용 해야 이전의 [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]합니다.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>참고 항목  
 [끌어서 놓기 작업 및 클립보드 지원](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)  
 [방법: 클립보드에서 데이터 검색](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)
