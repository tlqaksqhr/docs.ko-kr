---
title: Docker 컨테이너에 대해 .NET Core와 .NET Framework 중에 선택
description: 컨테이너화된 .NET 응용 프로그램에 대한 .NET 마이크로 서비스 아키텍처 | Docker 컨테이너에 대해 .NET Core와 .NET Framework 중에 선택
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: b483214e7bd039a71ae642aa26e69d63222af8ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a>Docker 컨테이너에 대해 .NET Core와 .NET Framework 중에 선택

.NET에서 서버 쪽 컨테이너화된 Docker 응용 프로그램을 구축하는 데 지원되는 두 가지 구현은 [.NET Framework](https://www.microsoft.com/net/download/framework) 및 [.NET Core](https://www.microsoft.com/net/download/core)입니다. 두 구현은 여러 .NET Standard 구성 요소를 공유하므로 둘 간에 코드를 공유할 수 있습니다. 그러나 두 구현 간에는 기본적인 차이가 있으며, 사용하는 구현은 수행하려는 작업에 따라 달라집니다. 이 섹션에서는 각 구현을 선택할 경우에 대한 지침을 제공합니다.


>[!div class="step-by-step"]
[이전](../container-docker-introduction/docker-containers-images-registries.md) [다음](general-guidance.md)
