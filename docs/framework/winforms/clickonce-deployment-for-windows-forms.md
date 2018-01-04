---
title: "Windows Forms에 대한 ClickOnce 배포"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ClickOnce deployment [Windows Forms]
- Windows Forms, ClickOnce deployment
- walkthroughs [Windows Forms], ClickOnce deployment
ms.assetid: 1451fce9-1965-4a03-b4d3-831b5fe4ad66
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1f157ea4afcaccfffde548c26a440fa6686c87aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="clickonce-deployment-for-windows-forms"></a>Windows Forms에 대한 ClickOnce 배포
다음 항목에서는 Windows Forms 응용 프로그램을 클라이언트 컴퓨터에 쉽게 배포하는 데 사용되는 기술인 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]를 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [ClickOnce 배포 전략 선택](/visualstudio/deployment/choosing-a-clickonce-deployment-strategy)  
 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 응용 프로그램을 배포하는 여러 가지 옵션을 제공합니다.  
  
 [ClickOnce 업데이트 전략 선택](/visualstudio/deployment/choosing-a-clickonce-update-strategy)  
 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 응용 프로그램을 업데이트하는 여러 가지 옵션을 제공합니다.  
  
 [ClickOnce 응용 프로그램 보안](/visualstudio/deployment/securing-clickonce-applications)  
 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 배포의 보안 관련 문제를 설명합니다.  
  
 [ClickOnce 배포 문제 해결](/visualstudio/deployment/troubleshooting-clickonce-deployments)  
 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 응용 프로그램 배포 시 발생할 수 있는 다양한 문제를 설명하고 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]에서 생성할 수 있는 최상위 오류 메시지를 문서화합니다.  
  
 [ClickOnce 및 응용 프로그램 설정](/visualstudio/deployment/clickonce-and-application-settings)  
 이후 검색을 위해 응용 프로그램 및 사용자 설정을 저장하는 응용 프로그램 설정을 통해 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 배포가 작동하는 방식을 설명합니다.  
  
 [신뢰할 수 있는 응용 프로그램 배포 개요](/visualstudio/deployment/trusted-application-deployment-overview)  
 클라이언트 컴퓨터에서 신뢰할 수 있는 응용 프로그램을 상위 권한 수준으로 실행할 수 있게 해주는 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 기능을 설명합니다.  
  
 [ClickOnce 및 Authenticode](/visualstudio/deployment/clickonce-and-authenticode)  
 신뢰할 수 있는 응용 프로그램 배포에서 Authenticode 기술을 사용하는 방법을 설명합니다.  
  
 [연습: ClickOnce 응용 프로그램 수동 배포](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)  
 Visual Studio를 사용하지 않고 명령줄 및 SDK 도구를 통해 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 응용 프로그램을 배포하는 방법을 보여 줍니다.  
  
 [방법: ClickOnce 응용 프로그램의 클라이언트 컴퓨터에 신뢰할 수 있는 게시자 추가](/visualstudio/deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications)  
 신뢰할 수 있는 응용 프로그램 배포에 필요한 클라이언트 컴퓨터의 일회성 구성을 보여 줍니다.  
  
 [방법: 배포 업데이트를 위한 대체 위치 지정](/visualstudio/deployment/how-to-specify-an-alternate-location-for-deployment-updates)  
 SDK 도구를 사용하여 다른 위치에서 응용 프로그램의 새 버전을 확인하도록 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 응용 프로그램을 구성하는 방법을 보여 줍니다.  
  
 [연습: ClickOnce 배포 API에서 요청 시 어셈블리 다운로드](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api)  
 응용 프로그램이 처음 로드하려고 시도할 때 API 호출을 사용하여 어셈블리를 검색하는 방법을 보여 줍니다.  
  
 [방법: 온라인 ClickOnce 응용 프로그램에서 쿼리 문자열 정보 검색](/visualstudio/deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application)  
 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 응용 프로그램을 실행하는 데 사용되는 URL에서 매개 변수를 검색하는 방법을 보여 줍니다.  
  
 [ClickOnce 캐시 개요](/visualstudio/deployment/clickonce-cache-overview)  
 로컬 컴퓨터에 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 응용 프로그램을 저장하는 데 사용되는 캐시를 설명합니다.  
  
 [ClickOnce 응용 프로그램의 로컬 및 원격 데이터 액세스](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications)  
 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 응용 프로그램에서 로컬 데이터 파일 및 원격 데이터 소스에 액세스하는 방법을 설명합니다.  
  
 [방법: ClickOnce 응용 프로그램에 데이터 파일 포함](/visualstudio/deployment/how-to-include-a-data-file-in-a-clickonce-application)  
 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 데이터 디렉터리에서 사용할 수 있도록 파일을 표시하는 방법을 보여 줍니다.  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램 설정 개요](../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [ClickOnce 응용 프로그램 게시](/visualstudio/deployment/publishing-clickonce-applications)  
 [명령줄에서 ClickOnce 응용 프로그램 빌드](/visualstudio/deployment/building-clickonce-applications-from-the-command-line)  
 [System.Deployment.Application을 사용하는 ClickOnce 응용 프로그램 디버그](http://msdn.microsoft.com/library/86f31948-2ca8-47c0-8e8b-c2b817bbf79f)  
 [ClickOnce를 사용하여 COM 구성 요소 배포](/visualstudio/deployment/deploying-com-components-with-clickonce)  
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)
