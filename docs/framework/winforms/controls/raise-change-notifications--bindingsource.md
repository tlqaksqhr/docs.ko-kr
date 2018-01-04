---
title: "방법: BindingSource와 INotifyPropertyChanged 인터페이스를 사용하여 변경 내용 알림 발생"
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
- change notifications [Windows Forms], raising
- BindingSource component [Windows Forms], and IPropertyChange
- data sources [Windows Forms], detecting changes
- examples [Windows Forms], BindingSource component
- change notifications
- INotifyPropertyChanged interface [Windows Forms], using with BindingSource
- BindingSource component [Windows Forms], examples
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3983b2544a4586f6f53e19a7f5fcdcd384a6bc2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a>방법: BindingSource와 INotifyPropertyChanged 인터페이스를 사용하여 변경 내용 알림 발생
데이터 소스에 포함된 형식이 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현하고 속성 값이 변경될 때 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 이벤트를 발생시키는 경우 <xref:System.Windows.Forms.BindingSource> 구성 요소가 데이터 소스의 변경 내용을 자동으로 검색합니다. 이 기능은 데이터 소스 값이 변경될 때 <xref:System.Windows.Forms.BindingSource>에 바인딩된 컨트롤이 자동으로 업데이트되므로 유용합니다.  
  
> [!NOTE]
>  데이터 소스가 <xref:System.ComponentModel.INotifyPropertyChanged>를 구현하고 비동기 작업을 수행하는 경우 백그라운드 스레드에서 데이터 소스를 변경하면 안 됩니다. 대신, 백그라운드 스레드에서 데이터를 읽은 다음 UI 스레드의 목록에 데이터를 병합해야 합니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스의 간단한 구현을 보여 줍니다. 또한 <xref:System.Windows.Forms.BindingSource>가 <xref:System.ComponentModel.INotifyPropertyChanged> 형식 목록에 바인딩된 경우 <xref:System.Windows.Forms.BindingSource>가 자동으로 데이터 소스 변경 내용을 바인딩된 컨트롤에 전달하는 방법을 보여 줍니다.  
  
 `CallerMemberName` 특성을 사용하는 경우 `NotifyPropertyChanged` 메서드 호출에서 속성 이름을 문자열 인수로 지정할 필요가 없습니다. 자세한 내용은 참조 [호출자 정보](http://msdn.microsoft.com/library/9cb2b8c0-c4f6-44b8-9c90-38948455b373)합니다.  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요. [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  또한 참조 [하이퍼링크 "http://msdn.microsoft.com/library/Bb129228 (v = vs.110)" 하는 방법: 컴파일 및 실행 전체 Windows Forms 코드 예제를 사용 하 여 Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ComponentModel.INotifyPropertyChanged>  
 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [방법: BindingSource ResetItem 메서드를 사용하여 변경 알림 발생](../../../../docs/framework/winforms/controls/how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
