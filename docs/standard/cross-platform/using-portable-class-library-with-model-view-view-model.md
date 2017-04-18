---
title: "Model-View-View Model과 함께 이식 가능한 클래스 라이브러리 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "이식 가능한 클래스 라이브러리 [.NET Framework] 및 MVVM"
  - "MVVM 및 이식 가능한 클래스 라이브러리"
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# Model-View-View Model과 함께 이식 가능한 클래스 라이브러리 사용
.NET Framework [휴대용 클래스 라이브러리](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) 를 사용하여 모델\-뷰\-뷰 모델 \(MVVM\) 패턴을 구현하고 여러 플랫폼에서 어셈블리를 공유할 수 있습니다.  
  
 MVVM은 내부 비즈니스 논리에서 사용자 인터페이스를 분리하는 응용 프로그램 패턴입니다.  특히  [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] 에서 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] 프로젝트에서 모델을 구현하고 모델 클래스를 본 다음, 여러 플랫폼을 위해 사용자 지정된 뷰를 만들 수 있습니다.  이 접근 방식을 사용하면 한 번만 데이터 모델과 비즈니스 논리를 작성하고 다음 그림처럼 .NET Framework, Silverlight, Windows Phone 및  [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램의 해당 코드를 사용할 수 있습니다.  
  
 ![MVVM 다이어그램으로 이식 가능](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")  
  
 이 항목에서는 MVVM 패턴에 대한 일반 정보를 제공하지 않습니다.  [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]을 사용하여 MVVM을 구현하는 방법에 대한 정보만 제공합니다.  MVVM에 대한 자세한 내용은 MSDN 라이브러리에 있는 [MVVM Quickstart](http://go.microsoft.com/fwlink/?LinkId=234934) 를 참조하십시오.  
  
## MVVM을 지원하는 클래스  
 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] 프로젝트에서 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight, 또는 Windows Phone 7.5를 대상으로 할 경우 다음 클래스는 MVVM 패턴을 구현하는 데 사용할 수 있습니다.  
  
-   <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=fullName> 클래스  
  
-   <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=fullName> 클래스  
  
-   <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=fullName> 클래스  
  
-   <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=fullName> 클래스  
  
-   <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=fullName> 클래스  
  
-   <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=fullName> 클래스  
  
-   <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=fullName> 클래스  
  
-   <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=fullName> 클래스  
  
-   <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=fullName> 클래스  
  
-   <xref:System.Windows.Input.ICommand?displayProperty=fullName> 클래스  
  
-   <xref:System.ComponentModel.DataAnnotations?displayProperty=fullName> 네임스페이스의 모든 클래스  
  
## MVVM 구현  
 MVVM을 구현하려면 일반적으로 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] 프로젝트의 뷰 모델과 모델을 모두 만들어야 합니다. 이는 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] 프로젝트에서 이식할 수 없는 프로젝트를 참조할 수 없기 때문입니다.  모델과 뷰 모델은 같은 프로젝트 또는 별도 프로젝트에서 수행될 수 있습니다.  별도 프로젝트를 사용하는 경우 뷰 모델 프로젝트에서 모델 프로젝트에 참조를 추가합니다.  
  
 모델을 컴파일하고 모델 프로젝트를 본 후에 뷰를 포함하는 응용 프로그램에서 이러한 어셈블리를 참조합니다.  뷰가 뷰 모델과만 상호 작용하는 경우 뷰 모델이 포함된 어셈블리만 참조해야 합니다.  
  
### 모델  
 다음 예제는 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] 프로젝트에 있을 수 있는 간단한 모델 클래스를 보여줍니다.  
  
 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]  
  
 다음 예제에서는 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] 프로젝트에서 데이터 채우기, 검색 및 업데이트 하는 간단한 방법을 보여줍니다.  실제 응용 프로그램에서 WCF\(Windows Communication Foundation\) 서비스 같은 소스에서 데이터를 검색합니다.  
  
 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]  
  
### 뷰 모델  
 뷰 모델에 대한 기본 클래스는 MVVM 패턴을 구현할 때 자주 추가됩니다.  다음 예제에서는 기본 클래스를 보여 줍니다.  
  
 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]  
  
 <xref:System.Windows.Input.ICommand> 인터페이스의 구현은 MVVM 패턴과 함께 자주 사용됩니다.  다음 예제에서는 <xref:System.Windows.Input.ICommand> 인터페이스의 구현을 보여 줍니다.  
  
 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]  
  
 다음 예제에서는 간단한 뷰 모델을 보여줍니다.  
  
 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### 보기  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 응용 프로그램, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램, Silverlight 기반 응용 프로그램 또는 Windows Phone 7.5 응용 프로그램에서 모델 및 뷰 모델 프로젝트를 포함하는 어셈블리를 참조할 수 있습니다.  그런 다음 뷰 모델과 상호 작용하는 뷰를 만듭니다.  다음 예제에서는 뷰 모델에서 데이터를 검색하고 업데이트 하는 간단한 WPF\(Windows Presentation Foundation\) 응용 프로그램을 보여줍니다.  Silverlight, Windows Phone 또는 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱에서 유사한 뷰를 만들 수 있습니다.  
  
 [!code-xml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## 참고 항목  
 [이식 가능한 클래스 라이브러리](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)