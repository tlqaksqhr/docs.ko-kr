---
title: "Windows 8, Windows 8.1 및 Windows 10에 .NET Framework 3.5 설치"
ms.date: 05/26/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
helpviewer_keywords:
- .NET Framework 3.5, installing on Windows 8
- Windows 8, installing .NET Framework 3.5
ms.assetid: 3eab3eb4-4573-42ac-98f8-36fb2c22c7d5
caps.latest.revision: 69
author: mairaw
ms.author: mairaw
ms.translationtype: HT
ms.sourcegitcommit: 20b0c1b36f705deb2f46ef4ab23653f829faf7ca
ms.openlocfilehash: 8a0395e28c01363eed27f327ea623feb4832c844
ms.contentlocale: ko-kr
ms.lasthandoff: 08/08/2017

---

# <a name="install-the-net-framework-35-on-windows-8-windows-81-and-windows-10"></a>Windows 8, Windows 8.1 및 Windows 10에 .NET Framework 3.5 설치

.NET Framework는 Windows에서 실행되는 대부분의 앱에서 필수적인 요소이며, 해당 앱이 실행되는 데 필요한 공통적인 기능을 제공합니다. 개발자의 경우 .NET Framework는 앱 빌드를 위한 일관된 프로그래밍 모델을 제공합니다. Windows 운영 체제를 사용하는 경우 .NET Framework가 이미 컴퓨터에 설치되었을 수 있습니다. 구체적으로 [!INCLUDE[win8](../../../includes/win8-md.md)]에는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]가 포함되어 있고, [!INCLUDE[win81](../../../includes/win81-md.md)]에는 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]이 포함되어 있으며, Windows 10에는 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]이 포함되어 있습니다.  
  
그러나 .NET Framework 3.5는 [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)] 또는 Windows 10과 함께 자동으로 설치되지 않으므로 이 버전에 종속된 앱을 실행하려면 별도로 사용하도록 설정해야 합니다. 이 작업은 세 가지 중 하나의 방법으로 호출되는 Windows 업데이트를 통해 수행해야 합니다. 이러한 모든 방법을 사용하려면 인터넷에 연결해야 합니다.  
  
- [요청 시 .NET Framework 3.5 설치](#OnDemand)  
  
- [제어판에서 .NET Framework 3.5를 사용하도록 설정](#ControlPanel)  
  
- [.NET Framework 3.5 설치 관리자 다운로드](http://www.microsoft.com/en-us/download/details.aspx?id=21) (참고: Windows 업데이트를 호출하는 설치 관리자로 .NET Framework를 직접 다운로드하지 않습니다.)  
  
설치 중 0x800f0906, 0x800f0907 또는 0x800f081f 오류가 발생할 수 있습니다. 이 경우 [.NET Framework 3.5 설치 오류: 0x800f0906, 0x800f0907 또는 0x800f081f](https://support.microsoft.com/en-us/kb/2734782)를 참조하세요. [보안 업데이트 3005628](https://support.microsoft.com/kb/3005628)을 설치하여 이러한 오류를 해결할 수 있습니다.  
  
위의 방법이 실패하거나 인터넷에 연결되지 않은 경우 Windows 설치 미디어를 사용해야 할 수 있습니다. 자세한 내용은 [.NET Framework 3.5 설치 오류 문서](https://support.microsoft.com/en-us/kb/2734782)에서 오류 0x800f0906에 대한 방법 3을 참조하세요. 설치 미디어가 없는 경우 [Windows 8.1용 설치 미디어 만들기](http://windows.microsoft.com/en-US/windows-8/create-reset-refresh-media?woldogcb=0)를 참조하세요.  
  
**유의 사항:**
  
- 일반적으로 컴퓨터에 설치되어 있는 .NET Framework 버전을 제거하지 마세요. 앱마다 다른 버전의 프레임워크를 사용하며, 단일 컴퓨터에서 여러 버전의 .NET Framework를 동시에 사용할 수 있습니다.  
  
- .NET Framework 3.5는 버전 2.0 및 3.0용으로 빌드된 앱에도 사용됩니다.  
  
- .NET Framework 3.5를 설치하기 전에 에 Windows 언어 팩을 설치하면 .NET Framework 3.5 설치에 실패할 수 있습니다. .NET Framework 3.5를 설치한 후에 Windows 언어 팩을 설치합니다.  
  
- Windows CardSpace는 [!INCLUDE[win8](../../../includes/win8-md.md)]에서 .NET Framework 3.5와 함께 사용할 수 없습니다.  
  
- .NET Framework 3.5를 설치하는 방법이 복잡하므로 Windows 업데이트와 별도로 실행할 수 있는 개별 독립 실행형 설치 관리자를 제공할 수 없습니다. 다른 모든 방법이 실패하는 경우에는 앞에서 설명한 대로 설치 미디어를 사용해야 합니다.  
  
<a name="OnDemand"></a>   
## <a name="install-the-net-framework-35-on-demand"></a>요청 시 .NET Framework 3.5 설치

앱에 .NET Framework 3.5가 필요하지만 컴퓨터에서 사용할 수 있는 해당 버전이 검색되지 않는 경우, 설치하는 동안이나 앱을 처음 실행할 때 다음과 같은 메시지 상자를 표시합니다. 메시지 상자에서 **이 기능 설치** 를 선택하여 .NET Framework 3.5를 사용하도록 설정합니다. 이 옵션을 사용하려면 인터넷에 연결해야 합니다.  
  
![Windows 8에 3.5 설치용 대화 상자](../../../docs/framework/deployment/media/installdialog.png "installdialog")  
  
<a name="ControlPanel"></a>   
## <a name="enable-the-net-framework-35-in-control-panel"></a>제어판에서 .NET Framework 3.5를 사용하도록 설정

제어판을 통해 .NET Framework 3.5를 사용하도록 설정할 수 있습니다. 이 옵션을 사용하려면 인터넷에 연결해야 합니다.  
  
1. 키보드에서 Windows 키 ![Windows 로고](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")를 누릅니다. “Windows 기능”을 입력하고 Enter 키를 누릅니다. **Windows 기능 사용/사용 안 함 대화 상자** 가 표시됩니다. 또는 제어판을 열고 **프로그램** 항목을 클릭한 다음, **프로그램 및 기능**에서 **Windows 기능 사용/사용 안 함**을 선택합니다.  
  
2. **.NET Framework 3.5(.NET 2.0 및 3.0 포함)** 확인란을 선택하고, **확인**을 선택하고, 메시지가 표시되면 컴퓨터를 다시 부팅합니다.  
  
WCF 스크립트 및 처리기 매핑 기능이 필요한 개발자가 아니라면 **WCF(Windows Communication Foundation ) HTTP Activation**을 위한 자식 항목을 선택할 필요가 없습니다.
  
## <a name="see-also"></a>참고 항목

[설치 가이드](../../../docs/framework/get-started/index.md)

