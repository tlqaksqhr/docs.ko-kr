---
title: "방법: 응용 프로그램 범위 리소스 사전 사용"
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
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ece6a5d2123bb118f11940081e3c1d939815a8ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>방법: 응용 프로그램 범위 리소스 사전 사용
이 예제에서는 응용 프로그램 범위 사용자 지정 리소스 사전을 정의하고 사용하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예  
 <xref:System.Windows.Application>공유 리소스에 대 한 응용 프로그램 범위 저장소는 노출: <xref:System.Windows.Application.Resources%2A>합니다. 기본적으로는 <xref:System.Windows.Application.Resources%2A> 의 인스턴스로 속성은 초기화는 <xref:System.Windows.ResourceDictionary> 유형입니다. 이 인스턴스를 사용 하 여 가져오고 사용 하 여 응용 프로그램 범위의 속성을 설정할 때 <xref:System.Windows.Application.Resources%2A>합니다. 자세한 내용은 참조 [하는 방법: 가져오기 및 설정 응용 프로그램 범위 리소스](http://msdn.microsoft.com/en-us/39e0420c-c9fc-47dc-8956-fdd95b214095)합니다.
  
 여러 리소스를 사용 하 여 설정한 경우 <xref:System.Windows.Application.Resources%2A>, 사용자 지정 리소스 사전을 해당 리소스를 저장 하 고 설정 하려면 대신 사용할 수 있습니다 <xref:System.Windows.Application.Resources%2A> 된 대신 합니다. 다음 XAML을 사용 하 여 사용자 지정 리소스 사전을 선언 하는 방법을 보여 줍니다.
  
 [!code-xaml[HOWTOResourceDictionaries#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 전체 리소스 사전을 사용 하 여 교환 <xref:System.Windows.Application.Resources%2A> 테마 마다 단일 리소스 사전에서 캡슐화 되어 있는 응용 프로그램 범위 테마가 지원 수 있습니다. 다음 예제에서는 <xref:System.Windows.ResourceDictionary>를 설정하는 방법을 보여 줍니다.  
  
 [!code-xaml[HOWTOResourceDictionaries#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 다음에 의해 노출 리소스 사전에서 응용 프로그램 범위 리소스를 가져오는 방법을 보여 줍니다. <xref:System.Windows.Application.Resources%2A> XAML에서 합니다.  
  
 [!code-xaml[HOWTOResourceDictionaries#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 다음 예제에서는 코드에서 리소스를 가져오는 방법을 보여 줍니다.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 사용 하는 경우를 확인 하려면 두 가지 고려 사항을 <xref:System.Windows.Application.Resources%2A>합니다. 먼저, 사전 *키* 은 개체를 설정 하 고 속성 값을 가져올 경우 정확히 동일한 개체 인스턴스를 사용 해야 합니다. 문자열을 사용할 경우 키는 대/소문자를 구분해야 합니다. 두 번째, 사전 *값* 가 속성 값을 가져올 때 값을 원하는 형식으로 변환 해야 하는 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.ResourceDictionary>  
 <xref:System.Windows.Application.Resources%2A>  
 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [병합된 리소스 사전](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)
