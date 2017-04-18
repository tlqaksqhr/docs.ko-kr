---
title: "방법: Net.TCP Port Sharing Service 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "포트 공유 [WCF]"
  - "활성화 서비스 [WCF]"
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# 방법: Net.TCP Port Sharing Service 사용
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]는 Net.TCP Port Sharing Service라고 하는 Windows 서비스를 사용하여 여러 프로세스에서 TCP 포트를 공유할 수 있습니다. 이 서비스는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 일부로 설치되지만 보안 예방 조치로 서비스가 기본적으로 활성화되지 않기 때문에 처음 사용하기 전에 수동으로 활성화해야 합니다. 이 항목에서는 MMC(Microsoft Management Console) 스냅인을 사용하여 Net TCP Port Sharing Service를 구성하는 방법에 대해 설명합니다.  
  
 Net.TCP 포트 공유 서비스를 사용 하 고 수동으로 시작 후 참조 [하는 방법: 포트 공유를 사용 하도록 WCF 서비스 구성](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) 이 서비스를 사용 하 여 서비스를 구성 하는 방법에 대 한 내용은 합니다.  
  
 Net.tcp:// 포트 공유를 사용 하는 샘플을 참조 하십시오.는 [Net.TCP Port Sharing 샘플](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md)합니다.  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a>MMC를 사용하여 Net.TCP Port Sharing Service를 사용하려면  
  
1.  시작 메뉴에서 명령 프롬프트 창을 열고 입력 하 여 서비스 관리 콘솔을 열고 `services.msc` 또는 실행을 열고 입력 하 여 `services.msc` 열기 상자에 있습니다.  
  
2.  에 **이름** 서비스 목록의 열을 마우스 오른쪽 단추로 클릭는 **Net.Tcp 포트 공유 서비스가**, 선택한 **속성** 메뉴에서 합니다.  
  
3.  에 서비스의 수동 시작을 사용 하도록 설정 하는 **속성** 창 선택은 **일반** 탭 및는 **시작 유형** 상자에서 수동을 선택한 다음 클릭 **적용**합니다.  
  
4.  서비스 상태 영역에는 서비스를 시작 하려면는 **시작** 단추입니다. 서비스 상태가 "시작됨"으로 표시되어야 합니다.  
  
5.  서비스 목록으로 돌아가려면 클릭는 **확인**, MMC 콘솔을 종료 합니다.  
  
## <a name="example"></a>예제  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
## <a name="see-also"></a>참고 항목  
 [Net.TCP 포트 공유](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)   
 [Net.TCP 포트 공유 서비스를 구성 합니다.](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)