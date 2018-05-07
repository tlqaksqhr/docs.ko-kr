---
title: Visual Studio 2012용 ID 및 액세스 도구
ms.date: 03/30/2017
ms.assetid: 87b8f8f2-4074-44fd-9fd6-08278e877390
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 107028b89d576b27a2559fd0ae5298c849da2c94
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="identity-and-access-tool-for-visual-studio-2012"></a>Visual Studio 2012용 ID 및 액세스 도구
이 항목에서는 Visual Studio 11에 대한 새로운 ID 및 액세스 도구에 대해 설명합니다. 다음 URL에서이 도구를 다운로드할 수 있습니다: [ http://go.microsoft.com/fwlink/?LinkID=245849 ](http://go.microsoft.com/fwlink/?LinkID=245849) 또는에서 직접 확장 관리자에서 직접 "id"를 검색 하 여 Visual Studio 11 내에서.  
  
 Visual Studio 11의 ID 및 액세스 도구는 다음과 같은 주요 기능과 함께 개발 시간이 크게 절감된 환경을 제공합니다.  
  
-   새로운 도구를 통해 웹 응용 프로그램 프로젝트 형식을 사용하여 개발하고 IIS Express를 대상으로 지정할 수 있습니다.  
  
-   블랭킷 보호 전용 인증과 달리, 새 도구를 사용하면 로컬 홈 영역 검색 페이지/컨트롤러 또는 응용 프로그램 내에서 인증 환경을 처리하는 다른 끝점을 지정할 수 있으며 WIF가 STS로 리디렉션하는 대신 인증되지 않은 모든 요청이 처리되도록 구성합니다.  
  
-   도구에는 디버그 세션을 시작할 때 로컬 컴퓨터에서 실행되는 STS(보안 토큰 서비스) 테스트가 포함되어 있습니다. 따라서 더 이상 사용자 지정 STS 프로젝트를 만들고 응용 프로그램을 테스트하는 데 필요한 클레임을 얻기 위해 해당 프로젝트를 수정할 필요가 없습니다. 클레임 형식과 값은 완전히 사용자 지정할 수 있습니다.  
  
-   web.config를 편집할 필요 없이 해당 도구의 UI를 통해 직접 일반적인 설정을 수정할 수 있습니다.  
  
-   한 화면에서 ADFS(Active Directory Federation Services) 2.0 또는 다른 WS-Federation 공급자와의 페더레이션을 설정할 수 있습니다.  
  
-   도구를 통해 Facebook, Google, Live ID, Yahoo!, OpenID 공급자 및 WS-Federation 공급자와 같이 사용하려는 모든 ID 공급자에 대한 간단한 확인란 목록과 함께 Microsoft Azure ACS(액세스 제어 서비스) 기능을 활용할 수 있습니다. ID 공급자를 선택하고, 확인을 클릭한 후 F5 키를 클릭하면 응용 프로그램과 ACS가 자동으로 구성되고 테스트 응용 프로그램이 ACS를 인식하게 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [WIF 기능](../../../docs/framework/security/wif-features.md)
