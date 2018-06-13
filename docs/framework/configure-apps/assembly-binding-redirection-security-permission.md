---
title: 어셈블리 바인딩 리디렉션 보안 권한
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ef9295028aeb7bfcc6df88e9c8bb7f80e2a31368
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743266"
---
# <a name="assembly-binding-redirection-security-permission"></a>어셈블리 바인딩 리디렉션 보안 권한
응용 프로그램 구성 파일에서 어셈블리 바인딩을 명시적으로 리디렉션하려면 보안 권한이 필요합니다. 이는 .NET Framework 어셈블리와 타사 어셈블리의 리디렉션 모두에 적용됩니다. 설정 하 여 권한 부여는 <xref:System.Security.Permissions.SecurityPermissionFlag> 에 플래그는 <xref:System.Security.Permissions.SecurityPermission>합니다. 관리 되는 어셈블리 기본적으로 권한이 없습니다.  
  
 신뢰할 수 있는 영역 (로컬 컴퓨터) 및 인트라넷 영역에서 실행 중인 응용 프로그램에는 보안 권한이 부여 됩니다. 인터넷 영역에서 실행 중인 응용 프로그램에서 어셈블리 바인딩 리디렉션을 수행할 금지 엄격 하 게 됩니다.  
  
 관리자에 의해 제어 되는 컴퓨터 구성 파일 또는 구성 요소 게시자에 의해 제어 되는 게시자 정책 파일에 어셈블리 리디렉션을 수행 되는 경우에 권한이 필요 하지 않습니다. 그러나 사용 권한을 명시적으로 사용 하 여 게시자 정책을 무시 하려면 응용 프로그램에 필요한는 [ \<예 = "no" / >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) 응용 프로그램 구성 파일의 요소입니다.  
  
 다음 표에서 기본 보안 설정에 대 한는 **이러한** 플래그입니다.  
  
|영역|이러한 플래그 설정|  
|----------|-----------------------------------|  
|신뢰할 수 있는 영역 (로컬 컴퓨터)|**ON**|  
|인트라넷 영역|**ON**|  
|인터넷 영역|**OFF**|  
|신뢰할 수 없는 영역|**OFF**|  
  
 관리자 또는 제한 지정된 된 컴퓨터의 특정 시나리오를 지원 하도록 이러한 보안 설정을 변경할 수 있습니다. 변경 하기 위한 도구도 **이러한** 플래그 설정을 기본;에서 관리자가 수동으로 편집 해야 Security.config 파일 사용자의 컴퓨터에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [게시자 정책 파일 및-병렬 실행](http://msdn.microsoft.com/library/97a042be-4d72-40c3-91c0-76fd36bdf133)  
 [방법: 자동 바인딩 리디렉션 사용 설정 및 해제](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)  
 [Side-by-Side 실행](../../../docs/framework/deployment/side-by-side-execution.md)
