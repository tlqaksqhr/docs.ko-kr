---
title: "방법: 형식에 Windows Forms 컨트롤 바인딩"
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
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d346e1f853d735e8aae0dd5647c14ac6eb8c237b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type"></a>방법: 형식에 Windows Forms 컨트롤 바인딩
데이터와 상호 작용하는 컨트롤을 빌드하는 경우 때로는 개체가 아니라 형식에 컨트롤을 바인딩할 필요가 있습니다. 이 상황은 특히 데이터를 사용할 수 없지만 데이터 바인딩된 컨트롤이 여전히 형식의 공용 인터페이스에서 가져온 정보를 표시해야 하는 경우 디자인 타임에 발생합니다. 예를 들어 웹 서비스에서 노출된 개체에 <xref:System.Windows.Forms.DataGridView> 컨트롤을 바인딩하고 디자인 타임에 <xref:System.Windows.Forms.DataGridView> 컨트롤이 사용자 지정 형식의 멤버 이름으로 해당 열의 레이블을 지정하도록 할 수 있습니다.  
  
 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 컨트롤을 형식에 쉽게 바인딩할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용자 지정 형식에 바인딩하는 방법을 보여 줍니다. 예제를 실행하면 컨트롤에 데이터가 채워지기 전에 <xref:System.Windows.Forms.DataGridView>에 `Customer` 개체의 속성을 반영하는 레이블 열이 포함됩니다. 예제에는 <xref:System.Windows.Forms.DataGridView> 컨트롤에 데이터를 추가하는 Add Customer 단추가 있습니다. 이 단추를 클릭하면 새로운 `Customer` 개체가 <xref:System.Windows.Forms.BindingSource>에 추가됩니다. 실제 시나리오에서는 웹 서비스 또는 다른 데이터 소스를 호출하여 데이터를 가져올 수 있습니다.  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요. [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)
