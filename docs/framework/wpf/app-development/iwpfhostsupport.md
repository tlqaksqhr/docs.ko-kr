---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 51964358d27a16d9840e29be06c11f57de2fad23
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="iwpfhostsupport"></a>IWpfHostSupport
응용 프로그램을 호스팅할 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] PresentationHost.exe 통해 콘텐츠를 호스트와 PresentationHost.exe 간의 통합 지점을 제공 하기 위해이 인터페이스를 구현 합니다.  
  
## <a name="remarks"></a>설명  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 웹 브라우저 같은 응용 프로그램에서 호스팅할 수 [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] 콘텐츠를 포함 하 여 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 느슨한 XAML 및 합니다. 호스트에 [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] 콘텐츠, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 응용 프로그램의 인스턴스를 만들는 [WebBrowser 컨트롤](http://go.microsoft.com/fwlink/?LinkId=97911)합니다. 호스팅할 수 [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] PresentationHost.exe 호스팅된 제공 하는의 인스턴스를 만들고 [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] 에 표시 하기 위해 호스트에 콘텐츠는 [WebBrowser 컨트롤](http://go.microsoft.com/fwlink/?LinkId=97911)합니다.  
  
 통합 사용 하 여 `IWpfHostSupport` PresentationHost.exe를 허용 합니다.  
  
-   검색 하 고 호스트 응용 프로그램은에 관심 있는 원시 입력된 장치 (휴먼 인터페이스 장치)에 등록 합니다.  
  
-   호스트 응용 프로그램으로 원시 입력된 장치를 등록된 하 고 적절 한 메시지 전달에서 입력된 메시지를 수신 합니다.  
  
-   사용자 지정 진행률과 오류 사용자 인터페이스에 대 한 호스트 응용 프로그램을 쿼리 합니다.  
  
> [!NOTE]
>  이 API는 로컬 클라이언트 컴퓨터에서만 사용할 수 있도록 지원됩니다.  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|[GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)|PresentationHost.exe가 호스트 응용 프로그램과 관련된 원시 입력 장치(휴먼 인터페이스 장치)를 검색할 수 있게 합니다.|  
|[FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)|E_NOTIMPL이 반환되지 않는 한 메시지를 받을 때마다 PresentationHost.exe에서 호출됩니다.|  
|[GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md)|기본적으로 PresentationHost.exe 자체 배포 진행률 및 배포 오류 사용자 인터페이스 제공 WPF 콘텐츠를 배포할 때 표시 되는 합니다.|
