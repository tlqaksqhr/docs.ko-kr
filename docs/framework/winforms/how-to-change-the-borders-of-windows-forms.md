---
title: '방법: Windows Forms의 테두리 변경'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 936d9d67454a272e79990f2e1b432391ecdc26a5
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-change-the-borders-of-windows-forms"></a>방법: Windows Forms의 테두리 변경
Windows Forms의 모양과 동작을 결정할 때 선택할 수 있는 여러 테두리 스타일이 있습니다. <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 속성을 변경하여 폼의 크기 조정 동작을 제어할 수 있습니다. 또한 <xref:System.Windows.Forms.Form.FormBorderStyle%2A>을 설정하면 캡션 표시줄 표시 방식 및 표시되는 단추에 영향을 줍니다. 자세한 내용은 <xref:System.Windows.Forms.FormBorderStyle>을 참조하세요.  
  
 Visual Studio에서는 이 작업이 광범위하게 지원됩니다.  
  
 참고 항목 [하는 방법: 디자이너를 사용 하 여 Windows Forms의 테두리 변경](http://msdn.microsoft.com/library/yettzh3e\(v=vs.110\))합니다.  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a>Windows Forms의 테두리 스타일을 프로그래밍 방식으로 설정하려면  
  
-   <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 속성을 원하는 스타일로 설정합니다. 폼의 테두리 스타일을 설정 하는 다음 코드 예제에서는 `DlgBx1` 를 <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>합니다.  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     또한 참조 [하는 방법: 디자인 타임에 대화 상자 만들기](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))합니다.  
  
     또한 테두리 스타일 옵션을 제공 하는 폼을 선택한 경우 **최소화** 및 **최대화** 단추를 사용 하려면 이러한 단추 중 하나 또는 모두 사용할지을 지정할 수 있습니다. 이러한 단추는 사용자 환경을 긴밀히 제어하려는 경우에 유용합니다. **최소화** 및 **최대화** 단추는 기본적으로 활성화 되어 있으며 해당 기능을 통해 조작는 **속성** 창.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.FormBorderStyle>  
 <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>  
 [Windows Forms 시작](../../../docs/framework/winforms/getting-started-with-windows-forms.md)
