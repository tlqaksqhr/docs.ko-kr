---
title: .NET Core 추가 도구
description: .NET Core 기능을 지원하고 확장하는 추가 도구에 대한 개요입니다.
author: mlacouture
ms.author: johalex
ms.date: 01/19/2018
ms.custom: mvc
ms.openlocfilehash: 5f744fd63116ac453a2a7db8eb94f12738c95f21
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36315201"
---
# <a name="net-core-additional-tools"></a><span data-ttu-id="8d5d6-103">.NET Core 추가 도구</span><span class="sxs-lookup"><span data-stu-id="8d5d6-103">.NET Core additional tools</span></span>

<span data-ttu-id="8d5d6-104">이 섹션에서는 [.NET Core CLI (명령줄 인터페이스)](..\tools\index.md) 도구 외에 .NET Core 기능을 지원하고 확장하는 도구 목록을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5d6-104">This section compiles a list of tools that support and extend the .NET Core functionality, in addition to the [.NET Core command-line interface (CLI)](..\tools\index.md) tools.</span></span>

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[<span data-ttu-id="8d5d6-105">WCF Web Service Reference 도구</span><span class="sxs-lookup"><span data-stu-id="8d5d6-105">WCF Web Service Reference tool</span></span>](wcf-web-service-reference-guide.md)

<span data-ttu-id="8d5d6-106">WCF(Windows Communication Foundation) Web Service Reference는 [Visual Studio 2017 버전 15.5](https://visualstudio.microsoft.com/news/releasenotes/vs2017-relnotes#WCFTools)에서 처음 공개된 Visual Studio 연결된 서비스 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="8d5d6-106">The WCF (Windows Communication Foundation) Web Service Reference is a Visual Studio connected service provider that made its debut in [Visual Studio 2017 version 15.5](https://visualstudio.microsoft.com/news/releasenotes/vs2017-relnotes#WCFTools).</span></span> <span data-ttu-id="8d5d6-107">이 도구는 현재 솔루션, 네트워크 위치 또는 WSDL 파일의 웹 서비스에서 메타 데이터를 검색하고, 해당 웹 서비스 작업을 액세스하는 데 사용할 수 있는 메서드와 함께 WCF 프록시 클래스를 정의하는 .NET Core 호환 소스 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5d6-107">This tool retrieves metadata from a web service in the current solution, on a network location, or from a WSDL file, and generates a source file compatible with .NET Core, defining a WCF proxy class with methods that you can use to access the web service operations.</span></span>

## <a name="wcf-dotnet-svcutil-tooldotnet-svcutil-guidemd"></a>[<span data-ttu-id="8d5d6-108">WCF dotnet-svcutil 도구</span><span class="sxs-lookup"><span data-stu-id="8d5d6-108">WCF dotnet-svcutil tool</span></span>](dotnet-svcutil-guide.md)

<span data-ttu-id="8d5d6-109">WCF(Windows Communication Foundation) dotnet-svcutil 도구는 네트워크 위치 또는 WSDL 파일의 웹 서비스에서 메타데이터를 검색하고, 해당 웹 서비스 작업을 액세스하는 데 사용할 수 있는 메서드와 함께 WCF 프록시 클래스를 정의하는 .NET Core 호환 소스 파일을 생성하는 .NET Core CLI 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="8d5d6-109">The WCF (Windows Communication Foundation) dotnet-svcutil tool is a .NET Core CLI tool that retrieves metadata from a web service on a network location or from a WSDL file, and generates a source file compatible with .NET Core, defining a WCF proxy class with methods that you can use to access the web service operations.</span></span> <span data-ttu-id="8d5d6-110">**dotnet-svcutil** 도구는 Visual Studio 2017 v15.5와 함께 처음 제공된 [**WCF Web Service Reference**](/dotnet/core/additional-tools/wcf-web-service-reference-guide) Visual Studio 연결 서비스 공급자에 대한 대체 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="8d5d6-110">The **dotnet-svcutil** tool is an alternative option to the [**WCF Web Service Reference**](/dotnet/core/additional-tools/wcf-web-service-reference-guide) Visual Studio connected service provider which first shipped with Visual Studio 2017 v15.5.</span></span> <span data-ttu-id="8d5d6-111">.NET Core CLI 도구인 **dotnet svcutil** 도구는 Linux, macOS, Windows에서 플랫폼 간에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d5d6-111">The **dotnet-svcutil** tool as a .NET Core CLI tool, is available cross-platform on Linux, macOS, and Windows.</span></span>

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[<span data-ttu-id="8d5d6-112">XML Serializer Generator</span><span class="sxs-lookup"><span data-stu-id="8d5d6-112">XML Serializer Generator</span></span>](xml-serializer-generator.md)

<span data-ttu-id="8d5d6-113">.NET Framework용 [Xml Serializer Generator(sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md)와 마찬가지로, [Microsoft.XmlSerializer.Generator NuGet 패키지](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator)는 .NET Core 및 .NET Standard 라이브러리용 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="8d5d6-113">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the solution for .NET Core and .NET Standard libraries.</span></span> <span data-ttu-id="8d5d6-114"><xref:System.Xml.Serialization.XmlSerializer>를 사용하여 해당 형식의 개체를 직렬화하거나 역직렬화할 때 XML serialization의 시작 성능을 향상시키기 위해 어셈블리에 포함된 형식의 XML serialization 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8d5d6-114">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>