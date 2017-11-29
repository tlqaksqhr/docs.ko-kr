---
title: "Windows Identity Foundation 4.5 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f723345-7270-49e2-b638-b3a34bd40517
caps.latest.revision: "11"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 312324553333427c08acf7ef3eb11059f2224d06
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="windows-identity-foundation-45-overview"></a>Windows Identity Foundation 4.5 개요
Windows Identity Foundation 4.5는 응용 프로그램에서 클레임 기반 ID를 구현하기 위한 일련의 .NET Framework 클래스입니다. 이를 사용하면 클레임 인식 응용 프로그램과 서비스의 이점을 더욱 쉽게 활용할 수 있습니다. WIF 4.5는 .NET Framework 버전 4.5 이상을 사용하는 웹 서비스 또는 웹 응용 프로그램에서 사용할 수 있습니다. WIF는 개방형 표준에 따라 공유 산업 비전을 구현하는 Microsoft 페더레이션 ID 소프트웨어 제품군의 일부분일 뿐입니다. 페더레이션 ID는 [AD FS(Active Directory® Federation Services)](http://go.microsoft.com/fwlink/?LinkID=247516) 2.0, [Microsoft Azure ACS(Access Control Services)](http://go.microsoft.com/fwlink/?LinkID=247517) 및 WIF와 같은 세 가지 구성 요소로 구성됩니다. 이러한 세 가지 구성 요소가 모여 Microsoft의 새로운 클레임 기반 클라우드 ID 및 액세스 플랫폼의 핵심을 형성합니다.  
  
 WIF에 대한 자세한 내용은 MSDN의 보안 개발자 센터에서 [Windows Identity Foundation 웹 사이트](http://go.microsoft.com/fwlink/?LinkId=149009)(http://go.microsoft.com/fwlink/?LinkId=149009)를 참조하세요. WIF를 사용하여 응용 프로그램 만들기에 대한 소개를 보려면 Vittorio Bertocci가 작성한 [Windows Identity Foundation 프로그래밍](http://go.microsoft.com/fwlink/?LinkId=210158)(http://go.microsoft.com/fwlink/?LinkId=210158)을 참조하세요(Microsoft Press에서 게시).  
  
## <a name="wif-45-features"></a>WIF 4.5 기능  
 WIF 4.5는 ID 인식 응용 프로그램을 만드는 데 사용되는 프레임워크입니다. 프레임워크는 WS-Trust 및 WS-Federation 프로토콜을 추상화하고, 개발자에게 클레임 인식 응용 프로그램을 구축하기 위한 API를 제공하며, 필요한 경우 STS(보안 토큰 서비스)를 제공합니다. 응용 프로그램에서 WIF를 사용하여 ADFS 2.0 및 ACS와 같은 STS에서 발급한 토큰을 처리하고, 웹 응용 프로그램 또는 웹 서비스에서 ID를 기반으로 결정을 내립니다.  
  
 WIF 4.5의 주요 기능은 다음과 같습니다.  
  
-   클레임 인식 응용 프로그램(신뢰 당사자 응용 프로그램)을 빌드합니다. WIF는 개발자가 클레임 인식 응용 프로그램을 작성하는 데 도움을 줍니다. 클레임 모델을 제공하는 것 외에도 클레임을 기반으로 사용자 액세스 결정을 수행할 수 있도록 응용 프로그램 개발자에게 다양한 API를 제공합니다.  또한 WIF는 ASP.NET 또는 WCF 환경에서 응용 프로그램을 빌드할 것인지 선택할 수 있도록 개발자에게 일관된 프로그래밍 환경을 제공합니다.  
  
-   클레임 인식 응용 프로그램에 ID 위임 지원을 빌드합니다.  WIF는 여러 서비스 경계를 넘어 원래 요청자의 ID를 유지 관리하는 기능을 제공 합니다. 이 기능은 프레임워크에서 "ActAs" 또는 "OnBehalfOf" 기능을 통해 사용할 수 있으며, 개발자에게 클레임 인식 응용 프로그램에 ID 위임 지원을 추가할 수 있는 기능을 제공합니다.  
  
-   사용자 지정 STS를 빌드합니다.  WIF를 사용하면 WS-Trust 프로토콜을 지원하는 사용자 지정 STS를 상당히 쉽게 빌드할 수 있습니다. 이러한 STS를 Active STS라고도 합니다.  
  
     또한, 프레임워크에서 웹 브라우저 클라이언트를 활성화할 수 있도록 WS-Federation을 지원하는 STS를 빌드할 수 있습니다. 이러한 STS를 Passive STS라고도 합니다.  
  
-   클레임 기반 ID를 사용하여 응용 프로그램을 보호하고 여러 ID 공급자의 사용자를 수락할 수 있도록 하는 Visual Studio 11의 새로운 ID와 액세스 도구입니다. 이 WIF 도구는 URL [http://go.microsoft.com/fwlink/?LinkID=245849](http://go.microsoft.com/fwlink/?LinkID=245849)에서 다운로드하거나, 확장 관리자에서 직접 “ID”를 검색하여 Visual Studio 11 내에서 바로 다운로드할 수 있습니다. 자세한 내용은 [Visual Studio 2012용 ID 및 액세스 도구](../../../docs/framework/security/identity-and-access-tool-for-vs.md)를 참조하세요.  
  
 WIF는 다음과 같은 주요 시나리오를 지원합니다.  
  
-   페더레이션  WIF를 사용하면 둘 이상의 파트너 간에 페더레이션을 사용할 수 있습니다. 클레임 인식 응용 프로그램(RP)과 사용자 지정 STS를 빌드할 수 있는 지원을 통해 개발자가 이 시나리오를 얻을 수 있습니다.  
  
-   ID 위임  WIF를 사용하면 개발자가 ID 위임 시나리오를 얻을 수 있도록 서비스 간에 ID를 쉽게 유지 관리할 수 있습니다.  
  
-   인증 강화 응용 프로그램 내의 리소스에 따라 인증 요구 사항이 달라질 수 있습니다. WIF를 통해 개발자가 증분 인증 요구 사항이 필요할 수 있는 응용 프로그램을 빌드할 수 있습니다(예: 사용자 이름/암호 인증으로 초기 로그인 후 스마트 카드 인증으로 강화).  
  
 WIF를 사용하여 클레임 기반 ID 모델의 이점을 쉽게 활용할 수 있습니다. 자세한 내용은 [개발자용 Windows Identity Foundation 백서](http://download.microsoft.com/download/7/d/0/7d0b5166-6a8a-418a-addd-95ee9b046994/windowsidentityfoundationwhitepaperfordevelopers-rtw.pdf)를 참조하세요.
