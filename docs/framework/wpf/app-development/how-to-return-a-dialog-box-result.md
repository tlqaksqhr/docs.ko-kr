---
title: "방법: 대화 상자 결과 반환 합니다."
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5f8133ffa7be9cb4e0600fc2681402d5e0f7471c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-return-a-dialog-box-result"></a>방법: 대화 상자 결과 반환 합니다.
호출 하 여 열려 있는 창에 대 한 대화 상자 결과 검색 하는 방법을 보여 주는이 예제 <xref:System.Windows.Window.ShowDialog%2A>합니다.  
  
## <a name="example"></a>예  
 대화 상자를 닫기 전에 해당 <xref:System.Windows.Window.DialogResult%2A> 속성으로 <xref:System.Nullable%601> <xref:System.Boolean> 사용자 대화 상자를 닫은 방법을 나타내는 합니다. 이 값이 반환 하 여 <xref:System.Windows.Window.ShowDialog%2A> 클라이언트 코드를 확인 하 여 대화 상자를 닫은 방법을 고 따라서 결과 처리 하는 방법입니다.  
  
> [!NOTE]
>  <xref:System.Windows.Window.DialogResult%2A>호출 하 여 창을 열린 경우에 설정할 수 <xref:System.Windows.Window.ShowDialog%2A>합니다.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 호출 <xref:System.Windows.Window.ShowDialog%2A> 모든 창과 사용자 입력된 이벤트를 제한 없이 사용할 수 있는 권한이 필요 합니다.
