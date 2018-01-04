---
title: "방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b314fe58413c0a284f5ebb41642e8c8dd1fb02b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거
Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤 데이터를 표시 하려면 열이 포함 되어야 합니다. 수동으로 컨트롤을 채우는 하려는 경우에 직접 열 추가 해야 있습니다. 또는 생성 하 고 열을 자동으로 채우는 데이터 소스에 컨트롤을 바인딩할 수 있습니다. 데이터 소스 표시 하려는 것 보다 많은 열이 있으면 필요 없는 열을 제거할 수 있습니다.  
  
 다음 절차를 필요는 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-add-a-column-using-the-designer"></a>디자이너를 사용 하 여 열을 추가 하려면  
  
1.  스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 오른쪽 위 모서리에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 다음 선택 **열 추가**합니다.  
  
2.  에 **열 추가** 대화 상자에서 선택 하는 **데이터 바인딩된 열** 옵션 및 데이터 원본에서 열을 선택 하거나 선택는 **바인딩되지 않은 열** 열을 정의 및 옵션 제공 된 필드를 사용 합니다.  
  
3.  클릭는 **추가** 이미 있는 기존 열 컨트롤 표시 영역을 채우지 않을 경우 디자이너에 표시 열을 추가 하려면 단추입니다.  
  
    > [!NOTE]
    >  열 속성을 수정할 수 있습니다는 **열 편집** 컨트롤의 스마트 태그에서 액세스할 수 있는 대화 상자.  
  
### <a name="to-remove-a-column-using-the-designer"></a>디자이너를 사용 하 여 열을 제거 하려면  
  
1.  선택 **열 편집** 컨트롤의 스마트 태그에서 합니다.  
  
2.  열을 선택 된 **선택한 열** 목록입니다.  
  
3.  클릭는 **제거** 단추 사라집니다 디자이너에서 열을 삭제 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
