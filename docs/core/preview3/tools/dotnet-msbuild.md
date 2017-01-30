---
title: "dotnet-msbuild 명령 | .NET Core SDK"
description: "dotnet-msmsbuild 명령은 MSmsbuild 명령줄에 대한 액세스 권한을 제공합니다."
keywords: "dotnet-msmsbuild, CLI, CLI 명령, .NET Core"
author: mairaw
manager: wpickett
ms.date: 10/13/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
translationtype: Human Translation
ms.sourcegitcommit: cde9d9577246a9025d646ce2a6d574a18512146e
ms.openlocfilehash: 51a3afdcf591b8147790d78471c6fee63ceb7f2d

---

#<a name="dotnet-msbuild"></a>dotnet-msbuild

## <a name="name"></a>이름 
dotnet-msbuild -- 프로젝트 및 모든 종속성을 빌드합니다. 

## <a name="synopsis"></a>개요

`dotnet msbuild <msbuild_arguments>`

## <a name="description"></a>설명
`dotnet msbuild` 명령을 사용하면 모든 기능을 갖춘 MSBuild에 액세스할 수 있습니다. 

명령에는 기존 MSBuild 명령줄 클라이언트와 정확히 동일한 기능이 있습니다. 옵션은 모두 동일합니다. 명령 참조에 익숙해지도록 [기존 설명서](https://msdn.microsoft.com/en-us/library/ms164311.aspx)를 사용할 수 있습니다. 

## <a name="examples"></a>예제

프로젝트 및 해당 종속성을 빌드합니다.

`dotnet msbuild`

릴리스 구성을 사용하여 프로젝트 및 해당 종속성을 빌드합니다.

`dotnet msbuild /p:Configuration=Release`

게시 대상을 실행하고 `osx.10.11-x64` RID에 대해 게시합니다.

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`



<!--HONumber=Nov16_HO3-->


