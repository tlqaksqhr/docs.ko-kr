---
title: "호스팅 예외 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 호스팅 예외
이 항목에서는 호스팅에 의해 생성된 모든 예외를 보여 줍니다.  
  
## 예외 목록  
  
|리소스 코드|리소스 문자열|  
|------------|-------------|  
|Hosting\_AddressIsAbsoluteUri|전체 URI가 허용되지 않습니다.ServiceHostingEnvironment.EnsureServiceAvailable API에는 전체 URI가 허용되지 않습니다.해당 서비스의 가상 경로를 사용하십시오.|  
|Hosting\_BuildProviderCouldNotCreateType|서비스를 컴파일하는 동안 지정된 CLR 형식을 로드할 수 없습니다.이 형식이 응용 프로그램의 \\\\App\_Code 디렉터리에 있는 소스 파일에 정의되어 있거나, 응용 프로그램의 \\\\bin 디렉토리에 있는 컴파일된 어셈블리에 포함되어 있거나, 전역 어셈블리 캐시에 설치된 어셈블리에 있는지 확인합니다.형식 이름은 대\/소문자를 구분합니다.\\\\App\_Code 및 \\\\bin 등의 디렉터리는 응용 프로그램의 루트 디렉터리에 있어야 합니다.\\\\App\_Code 및 \\\\bin 디렉터리는 하위 디렉터리에 중첩될 수 없습니다.|