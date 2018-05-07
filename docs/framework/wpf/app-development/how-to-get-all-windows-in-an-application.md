---
title: '방법: 응용 프로그램의 모든 창 가져오기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
ms.openlocfilehash: 476905899f5f7d573a16ba876c72f28ea34bbf9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-get-all-windows-in-an-application"></a>방법: 응용 프로그램의 모든 창 가져오기
이 예제에서는 모두 가져오기 위한 <xref:System.Windows.Window> 응용 프로그램의 개체입니다.  
  
## <a name="example"></a>예제  
 모든 인스턴스화할 <xref:System.Windows.Window> 개체를 볼 수 있는지 여부를 여부를 자동으로에서 관리 되는 창 참조의 컬렉션에 추가 됩니다 <xref:System.Windows.Application>에서 노출 하 고 <xref:System.Windows.Application.Windows%2A>합니다.  
  
 열거할 수 <xref:System.Windows.Application.Windows%2A> 다음 코드를 사용 하 여 인스턴스화된 모든 windows 얻으려고 합니다.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
