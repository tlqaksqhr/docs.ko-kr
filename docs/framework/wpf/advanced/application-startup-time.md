---
title: "응용 프로그램 시작 시간 | Microsoft Docs"
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
  - "응용 프로그램 시작[WPF]"
  - "성능[WPF], 시작 시간"
  - "시작 화면[WPF], 시작 시간"
  - "시작 시간[WPF]"
  - "WPF, 시작 시간"
ms.assetid: f0ec58d8-626f-4d8a-9873-c20f95e08b96
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 응용 프로그램 시작 시간
WPF 응용 프로그램이 시작되는 데 필요한 시간은 상황에 따라 크게 달라질 수 있습니다.  이 항목에서는 WPF\(Windows Presentation Foundation\) 응용 프로그램의 체감 시작 시간과 실제 시작 시간을 줄일 수 있는 여러 가지 기술에 대해 설명합니다.  
  
## 콜드 시작과 웜 시작 이해  
 콜드 시작은 시스템을 다시 부팅한 후 응용 프로그램을 처음 시작한 경우 또는 응용 프로그램을 시작하고 닫았다가 오랜 시간이 지난 후에 다시 시작한 경우에 발생합니다.  이 경우 응용 프로그램을 시작했을 때 코드, 정적 데이터, 레지스트리 등 필요한 페이지가 Windows 메모리 관리자의 대기 목록에 없으면 페이지 오류가 발생합니다.  페이지를 메모리로 가져오려면 디스크에 액세스해야 합니다.  
  
 웜 시작은 주 CLR\(공용 언어 런타임\) 구성 요소의 페이지 대부분이 메모리에 이미 로드되어 있을 때 발생하며 이 경우 비용이 많이 드는 디스크 액세스 시간을 줄일 수 있습니다.  관리되는 응용 프로그램을 두 번째 실행할 때 속도가 더 빠른 것도 이 때문입니다.  
  
## 시작 화면 구현  
 응용 프로그램을 시작한 후 첫 번째 UI가 표시될 때까지 작업이 오래 지연될 경우 *시작 화면*을 사용하여 체감 시작 시간을 최적화할 수 있습니다.  이 방법을 사용하면 사용자가 응용 프로그램을 시작함과 거의 동시에 이미지가 표시됩니다.  응용 프로그램에서 첫 번째 UI를 표시할 준비가 되면 시작 화면이 사라집니다.  [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]부터는 <xref:System.Windows.SplashScreen> 클래스를 사용하여 시작 화면을 구현할 수 있습니다.  자세한 내용은 [WPF 응용 프로그램에 시작 화면 추가](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md)를 참조하십시오.  
  
 네이티브 Win32 그래픽을 사용하여 사용자 고유의 시작 화면을 구현할 수도 있습니다.  이 구현은 <xref:System.Windows.Application.Run%2A> 메서드가 호출되기 전에 표시합니다.  
  
## 시작 코드 분석  
 콜드 시작이 느린 이유를 확인합니다.  디스크 I\/O 때문일 수 있지만 항상 그렇지는 않습니다.  일반적으로 네트워크, 웹 서비스 또는 디스크와 같은 외부 리소스의 사용을 최소화하는 것이 좋습니다.  
  
 테스트하기 전에 실행 중인 다른 응용 프로그램이나 서비스가 관리 코드나 WPF 코드를 사용하고 있지는 않은지 확인하십시오.  
  
 다시 부팅한 즉시 WPF 응용 프로그램을 시작하여 표시될 때까지 걸리는 시간을 확인합니다.  응용 프로그램을 두 번째 시작했을 때\(웜 시작\) 속도가 훨씬 빠르면 콜드 시작 문제의 원인이 I\/O일 가능성이 매우 큽니다.  
  
 응용 프로그램의 콜드 시작 문제가 I\/O와 관련되지 않은 경우에는 응용 프로그램에서 시간이 오래 소요되는 초기화 또는 계산을 수행하거나, 특정 이벤트가 완료될 때까지 기다리거나, 시작 시 많은 양의 JIT 컴파일이 필요한 것일 수 있습니다.  이와 같은 몇몇 경우에 대한 자세한 설명은 다음 단원을 참조하십시오.  
  
## 모듈 로드 최적화  
 Process Explorer\(Procexp.exe\) 및 Tlist.exe와 같은 도구를 사용하여 응용 프로그램에서 로드하는 모듈을 확인합니다.  `Tlist <pid>` 명령은 프로세스에서 로드하는 모든 모듈을 보여 줍니다.  
  
 예를 들어 웹에 연결하지 않는데도 System.Web.dll이 로드된다면 이 어셈블리를 참조하는 모듈이 응용 프로그램에 있는 것입니다.  이 경우 해당 참조가 필요한지 확인하십시오.  
  
 응용 프로그램에 모듈이 여러 개 있는 경우 단일 모듈로 병합하십시오.  이렇게 하면 CLR 어셈블리 로드 오버헤드를 줄일 수 있습니다.  어셈블리 수가 적으면 CLR에서 적은 수의 상태를 유지 관리하게 됩니다.  
  
## 초기화 작업 지연  
 주 응용 프로그램 창의 렌더링이 완료될 때까지 초기화 코드를 연기하는 것이 좋습니다.  
  
 클래스 생성자 내에서 초기화가 수행될 경우 초기화 코드가 다른 클래스를 참조하면 단계적 효과로 인해 클래스 생성자가 여러 개 실행될 수 있다는 점에 주의해야 합니다.  
  
## 응용 프로그램 구성 제한  
 응용 프로그램을 구성하지 않는 것이 좋습니다.  예를 들어 응용 프로그램에 대한 구성 요구 사항이 간단하고, 목표 시작 시간이 명확하게 정해진 경우에는 레지스트리 항목이나 간단한 INI 파일을 사용하여 시작하는 것이 더 빠를 수 있습니다.  
  
## GAC 사용  
 GAC\(전역 어셈블리 캐시\)에 어셈블리가 설치되어 있지 않으면 강력한 이름의 어셈블리에 대한 해시 유효성 검사 및 컴퓨터에 해당 어셈블리의 네이티브 이미지가 있는 경우 Ngen 이미지 유효성 검사로 인해 지연이 발생할 수 있습니다.  GAC에 설치된 모든 어셈블리에 대해서는 강력한 이름 확인이 생략됩니다.  자세한 내용은 [Gacutil.exe\(전역 어셈블리 캐시 도구\)](../../../../docs/framework/tools/gacutil-exe-gac-tool.md)를 참조하십시오.  
  
## Ngen.exe 사용  
 응용 프로그램에서 네이티브 이미지 생성기\(Ngen.exe\)를 사용하는 것이 좋습니다.  Ngen.exe를 통해 생성되는 네이티브 이미지는 일반적으로 MSIL 이미지보다 크기 때문에 Ngen.exe를 사용하면 CPU 사용이 줄어드는 대신 디스크 액세스가 많아질 수 있습니다.  
  
 웜 시작 시간을 줄이려면 응용 프로그램에서 항상 Ngen.exe를 사용하는 것이 좋습니다. 이렇게 하면 응용 프로그램 코드의 JIT 컴파일에 CPU가 사용되지 않습니다.  
  
 일부 콜드 시작 시나리오에서도 Ngen.exe를 사용하면 도움이 될 수 있습니다.  이는 JIT 컴파일러\(mscorjit.dll\)를 로드하지 않아도 되기 때문입니다.  
  
 Ngen과 JIT 모듈을 모두 사용하는 것은 최악의 시나리오가 될 수 있습니다.  이 경우 mscorjit.dll을 로드해야 하는데 코드에 대해 JIT 컴파일러 작업이 수행될 때 어셈블리의 메타데이터를 읽기 위해 Ngen 이미지의 여러 페이지에 액세스해야 하기 때문입니다.  
  
### Ngen 및 ClickOnce  
 응용 프로그램 배포 계획에 따라서도 로드 시간이 달라질 수 있습니다.  [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] 응용 프로그램 배포 방식을 사용할 경우에는 Ngen이 지원되지 않습니다.  따라서 응용 프로그램에 Ngen.exe를 사용하려면 Windows Installer와 같은 다른 배포 메커니즘을 사용해야 합니다.  
  
 자세한 내용은 [Ngen.exe\(네이티브 이미지 생성기\)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)를 참조하십시오.  
  
### 기준 재지정 및 DLL 주소 충돌  
 Ngen.exe를 사용하면 네이티브 이미지가 메모리에 로드될 때 기준이 다시 지정될 수 있습니다.  해당 주소 범위가 이미 할당되어 DLL을 기본 설정된 기준 주소에 로드할 수 없는 경우 Windows 로더는 DLL을 다른 주소에 로드하며 이 작업은 시간이 오래 걸릴 수 있습니다.  
  
 Virtual Address Dump\(Vadump.exe\) 도구를 사용하면 개인 페이지로만 된 모듈이 있는지 검사할 수 있습니다.  이러한 모듈이 있는 경우 해당 모듈은 다른 주소로 다시 지정되기 때문에  해당 페이지를 공유할 수 없습니다.  
  
 기준 주소 설정 방법에 대한 자세한 내용은 [Ngen.exe\(네이티브 이미지 생성기\)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)를 참조하십시오.  
  
## Authenticode 최적화  
 Authenticode 확인도 시작 시간이 길어지는 원인이 될 수 있습니다.  Authenticode 서명된 어셈블리는 CA\(인증 기관\)를 통해 확인되어야 합니다.  이 확인 작업을 수행하려면 최신 인증서 해지 목록을 다운로드하기 위해 네트워크에 여러 번 연결해야 하므로 시간이 오래 걸릴 수 있습니다.  또한 이 과정에서 신뢰할 수 있는 루트로 연결되는 경로에 대한 유효한 인증서가 모두 있는지도 확인합니다.  이로 인해 어셈블리가 로드되는 동안 몇 초 정도 작업이 지연될 수 있습니다.  
  
 클라이언트 컴퓨터에 CA 인증서를 설치하거나, 가능하면 Authenticode를 사용하지 않는 것이 좋습니다.  응용 프로그램에서 게시자 증명 정보를 필요로 하지 않는 경우 서명 확인에 리소스를 낭비할 필요가 없습니다.  
  
 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]부터는 Authenticode 확인을 건너뛸 수 있는 구성 옵션을 사용할 수 있습니다.  이렇게 하려면 app.exe.config 파일에 다음 설정을 추가하십시오.  
  
```  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>   
    </runtime>  
</configuration>  
```  
  
 자세한 내용은 [\<generatePublisherEvidence\> 요소](../../../../docs/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element.md)를 참조하십시오.  
  
## Windows Vista에서 성능 비교  
 Windows Vista의 메모리 관리자에는 SuperFetch라는 기술이 있습니다.  SuperFetch는 시간의 경과에 따른 메모리 사용 패턴을 분석하여 특정 사용자에 맞는 최적의 메모리 콘텐츠를 결정한 후  해당 콘텐츠를 지속적으로 유지 관리합니다.  
  
 이 방식은 Windows XP에서 사용 패턴에 대한 분석 없이 데이터를 메모리에 미리 로드하는 프리페치 기술과는 다릅니다.  시간이 지나면서 사용자가 Windows Vista에서 WPF 응용 프로그램을 자주 사용할 경우 응용 프로그램의 콜드 시작 시간이 단축될 수 있습니다.  
  
## 효율적인 AppDomain 사용  
 가능한 경우 응용 프로그램에서 만든 모든 AppDomain에서 네이티브 이미지\(있는 경우\)가 사용될 수 있도록 어셈블리를 도메인 중립 코드 영역에 로드하는 것이 좋습니다.  
  
 성능을 최대화하려면 도메인 간 호출을 줄여 도메인 간 통신의 효율성을 높이는 것이 좋습니다.  가능한 경우 인수 없는 호출을 사용하거나 기본 형식 인수를 사용하십시오.  
  
## NeutralResourcesLanguage 특성 사용  
 <xref:System.Resources.NeutralResourcesLanguageAttribute>를 사용하여 <xref:System.Resources.ResourceManager>에 대해 중립 문화권을 지정합니다.  이렇게 하면 어셈블리 조회 실패를 방지할 수 있습니다.  
  
## serialization에 BinaryFormatter 클래스 사용  
 serialization을 사용해야 할 경우 <xref:System.Xml.Serialization.XmlSerializer> 클래스 대신 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 클래스를 사용합니다.  <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 클래스는 mscorlib.dll 어셈블리의 BCL\(기본 클래스 라이브러리\)에 구현되는 반면  <xref:System.Xml.Serialization.XmlSerializer>는 System.Xml.dll 어셈블리에 구현되기 때문에 이 클래스를 사용할 경우 DLL을 추가로 로드해야 할 수 있습니다.  
  
 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 반드시 사용해야 할 경우에는 serialization 어셈블리를 미리 생성하여 성능을 높일 수 있습니다.  
  
## 시작된 후에 업데이트를 확인하도록 ClickOnce 구성  
 응용 프로그램에서 [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]를 사용하는 경우에는 응용 프로그램이 시작된 이후에 배포 사이트에서 업데이트를 확인하도록 [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]를 구성하여 응용 프로그램 시작 시에 네트워크 액세스가 발생하지 않도록 하는 것이 좋습니다.  
  
 XBAP\(XAML 브라우저 응용 프로그램\) 모델을 사용할 경우 [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]는 XBAP가 [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] 캐시에 이미 있는 경우에도 배포 사이트에서 업데이트를 확인한다는 점에 주의하십시오.  자세한 내용은 [ClickOnce 보안 및 배포](../Topic/ClickOnce%20Security%20and%20Deployment.md)를 참조하십시오.  
  
## PresentationFontCache 서비스가 자동으로 시작되도록 구성  
 다시 부팅한 이후 처음 실행되는 WPF 응용 프로그램은 PresentationFontCache 서비스입니다.  이 서비스는 시스템 글꼴을 캐시하고, 글꼴 액세스를 향상시키며 전반적인 성능을 높입니다.  이 서비스를 시작하는 데 오버헤드가 발생하므로 일부 제어된 환경에서만 시스템이 다시 부팅된 후 이 서비스가 자동으로 시작되도록 구성하는 것이 좋습니다.  
  
## 프로그래밍 방식으로 데이터 바인딩 설정  
 XAML을 사용하여 주 창에 대해 <xref:System.Windows.FrameworkElement.DataContext%2A>를 선언적으로 설정하는 대신 <xref:System.Windows.Application.OnActivated%2A> 메서드에 프로그래밍 방식으로 설정하십시오.  
  
## 참고 항목  
 <xref:System.Windows.SplashScreen>   
 <xref:System.AppDomain>   
 <xref:System.Resources.NeutralResourcesLanguageAttribute>   
 <xref:System.Resources.ResourceManager>   
 [WPF 응용 프로그램에 시작 화면 추가](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md)   
 [Ngen.exe\(네이티브 이미지 생성기\)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)   
 [\<generatePublisherEvidence\> 요소](../../../../docs/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element.md)