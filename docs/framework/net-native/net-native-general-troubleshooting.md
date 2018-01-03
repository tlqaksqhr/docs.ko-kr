---
title: ".NET 네이티브 일반 문제 해결"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee8c5e17-35ea-48a1-8767-83298caac1e8
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e92e99b978d12c32cc46b9133621875f35af634
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="net-native-general-troubleshooting"></a>.NET 네이티브 일반 문제 해결
이 항목에서는 [!INCLUDE[net_native](../../../includes/net-native-md.md)]를 사용하여 앱을 개발할 때 발생할 수 있는 잠재적인 문제를 해결하는 방법을 설명합니다.  
  
-   **문제:** 빌드 출력 창이 제대로 업데이트되지 않습니다.  
  
     **해결 방법:** 빌드 출력 창은 빌드가 완료될 때까지 업데이트되지 않습니다. 빌드 시간은 몇 분까지 걸릴 수 있으므로 업데이트 표시가 다소 지연될 수도 있습니다.  
  
-   **문제:** ARM의 앱 정품 빌드 시간이 길어졌습니다.  
  
     **해결 방법:** ARM 장치에 앱을 배포하는 경우 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 인프라가 호출됩니다. 이 컴파일에서는 리플렉션 등의 정적이 아닌 의미 체계가 계속 작동하도록 하는 동시에 많은 최적화를 수행합니다. 또한 성능을 최적화하기 위해 앱이 사용하는 .NET Framework 부분이 정적으로 연결되며, 이 부분 역시 네이티브 코드로 컴파일되어야 합니다. 이로 인해 컴파일 시간이 더 오래 걸립니다.  
  
     그러나 표준 개발 컴퓨터에서 대다수 앱의 표준 컴파일에 소요되는 컴파일 시간은 여전히 1분 이내입니다.  일반적으로 표준 개발 컴퓨터에서 .NET Framework용 네이티브 이미지를 생성하는 작업만 수행해도 몇 분이 걸립니다.  반면 생성된 코드를 개선하는 모든 최적화 작업과 .NET Framework 부분 컴파일 작업 시간을 모두 포함하더라도 앱 빌드 시간은 대개 1~2분에 불과합니다.  
  
     Microsoft는 다중 스레드 컴파일 및 기타 최적화를 조사하여 컴파일 성능을 개선하기 위해 지속적으로 노력하고 있습니다.  
  
-   **문제:** [!INCLUDE[net_native](../../../includes/net-native-md.md)]를 사용하여 앱을 컴파일했는지 여부를 알 수 없습니다.  
  
     **해결 방법:** [!INCLUDE[net_native](../../../includes/net-native-md.md)] 컴파일러를 호출하면 빌드 시간이 길어지며 작업 관리자에 ILC.exe 및 nutc_driver.exe와 같은 여러 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 구성 요소 프로세스가 표시됩니다.  
  
     [!INCLUDE[net_native](../../../includes/net-native-md.md)]를 사용하여 프로젝트를 정상적으로 빌드하고 나면 obj\\*config*\ *arch*\\*projectname*.ilc\out에서 출력을 확인할 수 있습니다.  최종 네이티브 패키지 콘텐츠는 bin\\*arch*\\*config*\AppX에서 확인할 수 있습니다. 앱을 배포한 경우 최종 네이티브 패키지 콘텐츠는 \bin\\*arch*\\*config*\AppX에 있습니다.  
  
-   **문제:** .NET 네이티브를 사용해서 컴파일한 앱에서 .NET 네이티브 없이 컴파일했을 때는 throw하지 않던 런타임 예외(일반적으로 [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) 또는 [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) 예외)를 throw합니다.  
  
     **해결 방법:** .NET 네이티브가 리플렉션을 통해 사용할 수 있는 구현 코드 또는 메타데이터를 제공하지 않았기 때문에 예외가 throw됩니다. (자세한 내용은 [.NET 네이티브 및 컴파일](../../../docs/framework/net-native/net-native-and-compilation.md)을 참조하세요.) 예외를 제거하려면 .NET 네이티브 도구 체인이 런타임에 메타데이터나 구현 코드를 사용 가능하게 만들 수 있도록 [런타임 지시문 파일(rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)에 항목을 추가해야 합니다. 런타임 지시문 파일에 추가할 필수 항목을 생성하는 데 두 가지 문제 해결사를 사용할 수 있습니다.  
  
    -   형식의 경우 [MissingMetadataException 문제 해결사](http://dotnet.github.io/native/troubleshooter/type.html) 입니다.  
  
    -   메서드의 경우 [MissingMetadataException 문제 해결사](http://dotnet.github.io/native/troubleshooter/method.html) 입니다.  
  
     자세한 내용은 [리플렉션 및 .NET 네이티브](../../../docs/framework/net-native/reflection-and-net-native.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Windows 스토어 앱을 .NET 네이티브로 마이그레이션](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)
