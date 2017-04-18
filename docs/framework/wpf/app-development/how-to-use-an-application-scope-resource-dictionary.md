---
title: "방법: 응용 프로그램 범위 리소스 사전 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "응용 프로그램 범위 리소스 사전"
  - "사전, 리소스"
  - "리소스 사전, 응용 프로그램 범위"
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 응용 프로그램 범위 리소스 사전 사용
이 예제에서는 응용 프로그램 범위 사용자 지정 리소스 사전을 정의하고 사용하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Application>은  공유 리소스인 <xref:System.Windows.Application.Resources%2A>에 대한 응용 프로그램 범위 저장소를 노출시킵니다.  기본적으로 <xref:System.Windows.Application.Resources%2A> 속성은 <xref:System.Windows.ResourceDictionary> 형식의 인스턴스로 초기화됩니다.  <xref:System.Windows.Application.Resources%2A>를 사용하여 응용 프로그램 범위 속성을 가져오고 설정할 때 이 인스턴스를 사용합니다.  자세한 내용은 [How to: Get and Set an Application\-Scope Resource](http://msdn.microsoft.com/ko-kr/39e0420c-c9fc-47dc-8956-fdd95b214095)을 참조하십시오.  
  
 <xref:System.Windows.Application.Resources%2A>를 사용하여 설정하는 리소스가 여러 개인 경우 사용자 지정 리소스 사전을 대신 사용하여 해당 리소스를 저장하고 <xref:System.Windows.Application.Resources%2A>를 설정할 수 있습니다.  다음 예제에서는 XAML을 사용하여 사용자 지정 리소스 사전을 선언하는 방법을 보여 줍니다.  
  
 [!code-xml[HOWTOResourceDictionaries#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <xref:System.Windows.Application.Resources%2A>를 사용하여 전체 리소스 사전을 맞바꾸면 응용 프로그램 범위, 테마를 지원할 수 있습니다. 이 경우 각 테마는 단일 리소스 사전에서 캡슐화합니다.  다음 예제에서는 <xref:System.Windows.ResourceDictionary>를 설정하는 방법을 보여 줍니다.  
  
 [!code-xml[HOWTOResourceDictionaries#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 다음 예제에서는 XAML의 <xref:System.Windows.Application.Resources%2A>에 의해 노출된 리소스 사전에서 응용 프로그램 범위 리소스를 가져오는 방법을 보여 줍니다.  
  
 [!code-xml[HOWTOResourceDictionaries#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 다음 예제에서는 코드에서 리소스를 가져오는 방법을 보여 줍니다.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <xref:System.Windows.Application.Resources%2A>를 사용할 때 다음 두 가지 사항을 고려해야 합니다.  먼저 사전 키는 개체이므로 속성 값을 설정하고 가져올 경우 정확히 같은 개체 인스턴스를 사용해야 합니다.  문자열을 사용할 경우 키는 대\/소문자를 구분해야 합니다. 두 번째로 사전 값은 개체이므로 속성 값을 가져올 경우 해당 값을 원하는 형식으로 변환해야 합니다.  
  
## 참고 항목  
 <xref:System.Windows.ResourceDictionary>   
 <xref:System.Windows.Application.Resources%2A>   
 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [병합된 리소스 사전](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)