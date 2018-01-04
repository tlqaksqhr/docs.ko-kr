---
title: "방법: 디자이너를 사용하여 ImageList 이미지 추가 또는 제거"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 05dd1e06c2cba31bca1282e8d409ab1b5610d1dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a>방법: 디자이너를 사용하여 ImageList 이미지 추가 또는 제거
이미지를 추가할 수는 <xref:System.Windows.Forms.ImageList> 여러 가지 방법으로 구성 합니다. 연결 된 스마트 태그를 사용 하 여 이미지를 매우 신속 하 게 추가할 수는 <xref:System.Windows.Forms.ImageList>에 다른 여러 속성을 설정 하는 경우 또는 <xref:System.Windows.Forms.ImageList>, 속성 창 사용 하 여 이미지를 추가 하는 편리한 방법을 찾을 수 있습니다. 코드를 사용 하 여 이미지를 추가할 수도 있습니다. 코드를 사용 하 여 이미지를 추가 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: Windows Forms ImageList 구성 요소와 이미지 추가 또는 제거](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)합니다. 채울 일반적으로 <xref:System.Windows.Forms.ImageList> 구성 요소를 이미지로 전에 컨트롤과 연결 되어 있지만이 필요 하지 않습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-add-or-remove-images-by-using-the-properties-window"></a>추가 하거나 속성 창을 사용 하 여 이미지를 제거 하려면  
  
1.  선택 된 <xref:System.Windows.Forms.ImageList> 구성 요소를 폼에 추가 하거나 합니다.  
  
2.  속성 창에서 줄임표 단추를 클릭 합니다. (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.ImageList.Images%2A> 속성입니다.  
  
3.  에 **이미지 컬렉션 편집기**, 클릭 **추가** 또는 **제거** 를 추가 하거나 목록에서 이미지를 제거 합니다.  
  
### <a name="to-add-or-remove-images-using-the-smart-tag"></a>스마트 태그를 사용 하 여 이미지 추가 또는 제거 하려면  
  
1.  선택 된 <xref:System.Windows.Forms.ImageList> 구성 요소를 폼에 추가 하거나 합니다.  
  
2.  스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))  
  
3.  에 **ImageList 작업** 대화 상자에서 **이미지 선택**합니다.  
  
4.  에 **이미지 컬렉션 편집기** 클릭 **추가** 또는 **제거** 를 추가 하거나 목록에서 이미지를 제거 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 [ImageList 구성 요소](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
