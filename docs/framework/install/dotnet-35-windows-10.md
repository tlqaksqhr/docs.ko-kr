---
title: "Windows 10, Windows 8.1 및 Windows 8에 .NET Framework 3.5 설치"
description: "Windows 10, Windows 8.1 및 Windows 8에 .NET Framework 3.5를 설치하는 방법을 알아봅니다."
author: rlander
ms.author: mairaw
keywords: ".Net Framework, 설치"
ms.date: 05/26/2017
ms.topic: article
ms.prod: .net-framework
ms.technology: vs-ide-deployment
ms.devlang: dotnet
ms.assetid: 67cda1d5-c6g4-4eb5-93e6-4f478de07ff7
ms.translationtype: HT
ms.sourcegitcommit: 21c6a1485f3d0c38bde065d6ecc7b07d5e424c1d
ms.openlocfilehash: 85a3cada074714c24015d90c26d94551f4f411f2
ms.contentlocale: ko-kr
ms.lasthandoff: 08/05/2017

---

# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a>Windows 10, Windows 8.1 및 Windows 8에 .NET Framework 3.5 설치

Windows 10, Windows 8.1 및 Windows 8에서 앱을 실행하려면 .NET Framework 3.5가 필요할 수 있습니다. 이러한 지침은 이전 Windows 버전에도 사용할 수 있습니다.

## <a name="install-the-net-framework-35-on-demand"></a>요청 시 .NET Framework 3.5 설치

.NET Framework 3.5가 필요한 앱을 실행하려고 하면 다음 구성 대화 상자가 표시될 수 있습니다. **이 기능 설치**를 선택하여 .NET Framework 3.5를 사용하도록 설정합니다. 이 옵션을 사용하려면 인터넷에 연결해야 합니다.

![.NET Framework 설치 대화 상자](./media/dotnet-framework-installation-dialog.jpg)

## <a name="enable-the-net-framework-35-in-control-panel"></a>제어판에서 .NET Framework 3.5를 사용하도록 설정

Windows 제어판을 통해 .NET Framework 3.5를 사용하도록 설정할 수 있습니다. 이 옵션을 사용하려면 인터넷에 연결해야 합니다.

1. 키보드에서 Windows 키 ![Windows 로고](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg)를 누르고, “Windows 기능”을 입력한 후 Enter 키를 누릅니다. **Windows 기능 사용/사용 안 함** 대화 상자가 나타납니다.

2. **.NET Framework 3.5(.NET 2.0 및 3.0 포함)** 확인란을 선택하고, **확인**을 선택하고, 메시지가 표시되면 컴퓨터를 다시 부팅합니다.

   ![제어판으로 .NET 설치](./media/dotnet-control-panel.png)

   이 기능이 필요한 개발자 또는 서버 관리자가 아니라면 **WCF(Windows Communication Foundation) HTTP 활성화** 및 **WCF(Windows Communication Foundation) 비 HTTP 활성화**를 위한 자식 항목을 선택할 필요가 없습니다.

