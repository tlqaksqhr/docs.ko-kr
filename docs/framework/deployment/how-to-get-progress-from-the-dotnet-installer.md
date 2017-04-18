---
title: "방법: .NET Framework 4.5 설치 관리자에서 진행률 가져오기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - ".NET Framework, 설치"
  - "진행률 정보, .NET Framework 설치 관리자"
ms.assetid: 0a1a3ba3-7e46-4df2-afd3-f3a8237e1c4f
caps.latest.revision: 30
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 30
---
# 방법: .NET Framework 4.5 설치 관리자에서 진행률 가져오기
The [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]는 재배포 가능 런타임입니다.  .NET Framework의 버전을 위한 응용 프로그램을 개발하는 경우, 응용 프로그램 설치 필수적인 부분으로 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치를 포함\(연결\)시킬 수 있습니다.  사용자 지정되거나 통합된 설치 환경을 제공하려는 경우 응용 프로그램의 설치 진행률을 표시하면서 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치 프로세스를 자동으로 시작하고 그 진행률을 추적할 수 있습니다.  자동 추적을 활성화하려면 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치 프로세스\(감시 대상\)에서 설치 프로세스\(감시자 또는 체이너\)와 통신하도록 MMIO\(메모리 매핑된 I\/O\) 세그먼트를 사용하여 프로토콜을 정의합니다.  이 프로토콜은 체이너가 진행률 정보를 획득하고 세부 결과를 얻고 메시지에 응답하며 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치를 취소하는 방법을 정의합니다.  
  
-   **호출**.  [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치를 호출하여 MMIO 섹션에서 진행률 정보를 받으려면 설치 프로그램에서 다음을 수행해야 합니다.  
  
    1.  [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 재배포 가능 프로그램을 호출합니다.  
  
        ```  
        dotNetFx45_Full_x86_x64.exe /q /norestart /pipe section-name  
        ```  
  
         여기서 *section name* 은 응용 프로그램을 식별하는 데 사용할 이름입니다. .NET Framework 설치에서는 MMIO 섹션에 대한 읽기 및 쓰기를 비동기적으로 수행하므로 해당 기간에 이벤트 및 메시지를 사용하기가 편리한 경우도 있습니다.  예제에서 .NET Framework 설치 프로세스는 MMIO 섹션\(`TheSectionName`\)을 할당하고 이벤트\(`TheEventName`\)를 정의하는 생성자에서 만들어집니다.  
  
        ```  
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName")  
        ```  
  
         해당 이름을 설치 프로그램에 고유한 이름으로 바꾸십시오.  
  
    2.  MMIO 섹션에서 읽습니다.  [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 다운로드 및 설치 작업은 동시에 진행됩니다. 따라서 .NET Framework에서 하나의 구성 요소를 설치하면서 다른 구성 요소를 다운로드할 수 있습니다.  따라서 진행률은 0에서 255로 증가하는 `m_downloadSoFar`와 `m_installSoFar` 두 개의 숫자로 MMIO 섹션에 다시 보내져 기록됩니다.  255가 작성되어 .NET Framework가 종료되면 설치가 완료됩니다.  
  
-   **종료 코드**.  명령에서 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 재배포 가능 프로그램을 호출하는 다음 종료 코드는 설치 프로그램의 성공 여부를 나타냅니다.  
  
    -   0 \- 설치가 성공적으로 완료되었습니다.  
  
    -   3010 – 설치가 완료되었습니다. 다시 시작해야 합니다.  
  
    -   1602 – 설치가 취소되었습니다.  
  
    -   기타 모든 코드 \- 설치하는 동안 오류가 발생했습니다. 자세한 내용은 %temp%에 만들어진 로그 파일을 참조하십시오.  
  
-   **설치 취소**.  MMIO 섹션에서 `m_downloadAbort` 및 `m_ installAbort` 플래그를 설정하는 `Abort` 메서드를 사용하여 언제든지 설치를 취소할 수 있습니다.  
  
## 체이너 샘플  
 체이너 샘플이 자동으로 시작되고 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치 프로그램의 진행 상황을 표시하면서 설치를 추적합니다.  이 샘플은 .NET Framework 4에 공급된 체이너 샘플과 유사합니다.  그러나 이 뿐만 아니라 .NET Framework 4 응용 프로그램을 닫기 위해 메시지 상자를 처리함으로써 시스템이 다시 시작되는 것을 방지할 수 있습니다.  이 메시지 상자에 대한 자세한 내용은 [.NET Framework 4.5를 설치하는 동안 시스템 다시 시작 줄이기](../../../docs/framework/deployment/reducing-system-restarts.md)을 참조하십시오.  .NET Framework 4 설치 관리자를 사용하여 이 샘플을 사용할 수 있습니다. 이 시나리오에서 메시지는 단순히 전송되지 않습니다.  
  
> [!WARNING]
>  이 예제는 관리자 권한으로 실행해야 합니다.  
  
 MSDN 샘플 갤러리에서 [.NET Framework 4.5 Chainer Sample](http://go.microsoft.com/fwlink/?LinkId=231345) 을 위한 완벽한 Visual Studio 솔루션을 다운로드 할 수 있습니다.  
  
 다음 단원에서는 이 샘플에서 중요한 파일을 설명합니다\(예: MMIOChainer.h, ChainingdotNet4.cpp, and IProgressObserver.h\).  
  
#### MMIOChainer.h  
  
-   MmIoChainer.h\( [complete code](http://go.microsoft.com/fwlink/?LinkId=231369)를 보세요\) 파일에는 체이너 클래스가 파생되어야 하는 데이터 구조 정의와 기본 클래스가 포함되어 있습니다.  [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]는 MMIO 데이터 구조를 확장하여 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치 관리자에게 필요한 데이터를 처리합니다.  MMIO 구조의 변경은 이전 버전과 호환되므로 .NET Framework 4 체이너는 다시 컴파일할 필요 없이 .NET Framework 4.5 설치 작업을 수행할 수 있습니다.  그러나, 이 시나리오는 시스템이 다시 시작되는 사례를 줄이기 위한 기능을 지원하지 않습니다.  
  
     버전 필드는 구조 및 메시지 형식으로 수정 버전을 식별하는 방법을 제공합니다.  .NET Framework 설치는 파일 매핑의 크기를 결정하는 `VirtualQuery` 함수를 호출하여 체이너 인터페이스의 버전을 확인합니다.  버전 필드를 수용하기에 크기가 충분히 큰 경우 .NET Framework 설치는 지정된 값을 사용합니다.  .NET Framework 4의 경우처럼 버전 필드를 포함하기에 파일 매핑이 너무 작은 경우 설치 프로세스는 버전 0 \(4\)으로 간주합니다.  체이너가 .NET Framework 설치에서 보내려는 메시지 버전을 지원하지 않을 경우 .NET Framework 설치는 무시 응답을 가정합니다.  
  
     MMIO 데이터 구조는 다음과 같이 정의됩니다.  
  
    ```cpp  
    // MMIO data structure for interprocess communication  
        struct MmioDataStructure  
        {  
            bool m_downloadFinished;               // Is download complete?  
            bool m_installFinished;                // Is installation complete?  
            bool m_downloadAbort;                  // Set to cause downloader to abort.  
            bool m_installAbort;                   // Set to cause installer to abort.  
            HRESULT m_hrDownloadFinished;          // Resulting HRESULT for download.  
            HRESULT m_hrInstallFinished;           // Resulting HRESULT for installation.  
            HRESULT m_hrInternalError;  
            WCHAR m_szCurrentItemStep[MAX_PATH];  
            unsigned char m_downloadSoFar;         // Download progress 0-255 (0-100% done).   
            unsigned char m_installSoFar;          // Installation progress 0-255 (0-100% done).  
            WCHAR m_szEventName[MAX_PATH];         // Event that chainer creates and chainee opens to sync communications.  
  
            BYTE m_version;                        // Version of the data structure, set by chainer:  
                                                   // 0x0: .NET Framework 4   
                                                   // 0x1: .NET Framework 4.5  
  
            DWORD m_messageCode;                   // Current message sent by the chainee; 0 if no message is active.  
            DWORD m_messageResponse;               // Chainer's response to current message; 0 if not yet handled.  
            DWORD m_messageDataLength;             // Length of the m_messageData field, in bytes.  
            BYTE m_messageData[1];                 // Variable-length buffer; content depends on m_messageCode.  
        };  
  
    ```  
  
-   `MmioDataStructure` 데이터 구조는 직접 사용해서는 안 되며 체이너를 구현하기 위해 `MmioChainer` 클래스를 대신 사용합니다.  `MmioChainer` 클래스에서 파생하여 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 재배포 가능 패키지에 연결합니다.  
  
#### IProgressObserver.h  
  
-   IProgressObserver.h 파일은 진행률 관찰자를 실행합니다.\([전체 코드보기](http://go.microsoft.com/fwlink/?LinkId=231370)\).  이 관찰자에게 다운로드와 설치 진행률을 알려줍니다\(1%\-100% 완료를 나타내는 부호가 없는 `char`, 0\-255로 지정\).  관찰자는 체이니가 메시지를 보낼 때도 알림을 받으며 관찰자는 응답을 보내야 합니다.  
  
    ```cpp  
        class IProgressObserver  
        {  
        public:  
            virtual void OnProgress(unsigned char) = 0; // 0 - 255:  255 == 100%  
            virtual void Finished(HRESULT) = 0;         // Called when operation is complete    
            virtual DWORD Send(DWORD dwMessage, LPVOID pData, DWORD dwDataLength) = 0; // Called when a message is sent  
        };  
  
    ```  
  
#### ChainingdotNet4.5.cpp  
  
-   이 [ChainingdotNet4.5.cpp](http://go.microsoft.com/fwlink/?LinkId=231368) 파일은 `MmioChainer` 클래스에서 파생되는 `Server` 클래스를 구현하고 진행률 정보를 표시하기 위해 적절한 메서드를 재정의합니다.  MmioChainer는 지정된 섹션 이름을 가진 섹션을 만들고 지정된 이벤트 이름을 사용하여 체이너를 초기화합니다.  이벤트 이름은 매핑된 데이터 구조에 저장됩니다.  섹션 이름과 이벤트 이름을 고유하게 만들어야 합니다.  다음 코드에서 `Server` 클래스는 지정된 설치 프로그램을 시작하여 진행률을 모니터링하며 종료 코드를 반환합니다.  
  
    ```cpp  
    class Server : public ChainerSample::MmioChainer, public ChainerSample::IProgressObserver  
    {  
    public:  
        …………….  
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName") //customize for your event names  
        {}  
  
    ```  
  
     설치는 Main 메서드에서 시작됩니다.  
  
    ```cpp  
    // Main entry point for program  
    int __cdecl main(int argc, _In_count_(argc) char **_argv)  
    {  
        int result = 0;  
        CString args;  
        if (argc > 1)  
        {  
            args = CString(_argv[1]);  
        }  
  
        if (IsNetFx4Present(NETFX45_RC_REVISION))  
        {  
            printf(".NET Framework 4.5 is already installed");  
        }  
        else  
        {  
            result = Server().Launch(args);  
        }  
  
        return result;  
    }  
  
    ```  
  
-   설치를 시작하기 전에 체이너는 `IsNetFx4Present`을 호출하여 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]가 이미 설치되었는지 확인합니다.  
  
    ```cpp  
    ///  Checks for presence of the .NET Framework 4.  
    ///    A value of 0 for dwMinimumRelease indicates a check for the .NET Framework 4 full  
    ///    Any other value indicates a check for a specific compatible release of the .NET Framework 4.  
    #define NETFX40_FULL_REVISION 0  
    // TODO: Replace with released revision number  
    #define NETFX45_RC_REVISION MAKELONG(50309, 5)   // .NET Framework 4.5   
    bool IsNetFx4Present(DWORD dwMinimumRelease)  
    {  
        DWORD dwError = ERROR_SUCCESS;  
        HKEY hKey = NULL;  
        DWORD dwData = 0;  
        DWORD dwType = 0;  
        DWORD dwSize = sizeof(dwData);  
  
        dwError = ::RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full", 0, KEY_READ, &hKey);  
        if (ERROR_SUCCESS == dwError)  
        {  
            dwError = ::RegQueryValueExW(hKey, L"Release", 0, &dwType, (LPBYTE)&dwData, &dwSize);  
  
            if ((ERROR_SUCCESS == dwError) && (REG_DWORD != dwType))  
            {  
                dwError = ERROR_INVALID_DATA;  
            }  
            else if (ERROR_FILE_NOT_FOUND == dwError)  
            {  
                // Release value was not found, let's check for 4.0.  
                dwError = ::RegQueryValueExW(hKey, L"Install", 0, &dwType, (LPBYTE)&dwData, &dwSize);  
  
                // Install = (REG_DWORD)1;  
                if ((ERROR_SUCCESS == dwError) && (REG_DWORD == dwType) && (dwData == 1))  
                {  
                    // treat 4.0 as Release = 0  
                    dwData = 0;  
                }  
                else  
                {  
                    dwError = ERROR_INVALID_DATA;  
                }  
            }  
        }  
  
        if (hKey != NULL)  
        {  
            ::RegCloseKey(hKey);  
        }  
  
        return ((ERROR_SUCCESS == dwError) && (dwData >= dwMinimumRelease));  
    }  
  
    ```  
  
-   정확한 위치를 가리키도록 `Launch` 메서드에서 실행 파일\(예제의 Setup.exe\)의 경로를 변경하거나 위치를 파악할 코드를 사용자 지정할 수 있습니다.  `MmioChainer` 기본 클래스는 파생 클래스를 호출하는 차단 `Run()` 메서드를 제공합니다.  
  
    ```cpp  
  
    bool Launch(const CString& args)  
    {  
    CString cmdline = L"dotNetFx45_Full_x86_x64.exe -pipe TheSectionName " + args; // Customize with name and location of setup .exe that you want to run  
    STARTUPINFO si = {0};  
    si.cb = sizeof(si);  
    PROCESS_INFORMATION pi = {0};  
  
    // Launch the Setup.exe that installs the .NET Framework 4.5  
    BOOL bLaunchedSetup = ::CreateProcess(NULL,   
     cmdline.GetBuffer(),  
     NULL, NULL, FALSE, 0, NULL, NULL,   
     &si,  
     &pi);  
  
    // If successful   
    if (bLaunchedSetup != 0)  
    {  
    IProgressObserver& observer = dynamic_cast<IProgressObserver&>(*this);  
    Run(pi.hProcess, observer);  
  
    ……………………..   
    return (bLaunchedSetup != 0);  
    }  
  
    ```  
  
-   `Send` 메서드가 메시지를 차단하고 처리합니다.  이 버전의 .NET Framework에서 지원되는 유일한 메시지는 닫기 응용 프로그램 메시지입니다.  
  
    ```cpp  
            // SendMessage  
            //  
            // Send a message and wait for the response.  
            // dwMessage: Message to send  
            // pData: The buffer to copy the data to  
            // dwDataLength: Initially a pointer to the size of pBuffer.  Upon successful call, the number of bytes copied to pBuffer.  
            //--------------------------------------------------------------  
        virtual DWORD Send(DWORD dwMessage, LPVOID pData, DWORD dwDataLength)  
        {  
            DWORD dwResult = 0;  
            printf("recieved message: %d\n", dwMessage);  
            // Handle message  
            switch (dwMessage)  
            {  
            case MMIO_CLOSE_APPS:  
                {  
                    printf("    applications are holding files in use:\n");  
                    IronMan::MmioCloseApplications* applications = reinterpret_cast<IronMan::MmioCloseApplications*>(pData);  
                    for(DWORD i = 0; i < applications->m_dwApplicationsSize; i++)  
                    {  
                        printf("      %ls (%d)\n", applications->m_applications[i].m_szName, applications->m_applications[i].m_dwPid);  
                    }  
  
                    printf("    should appliations be closed? (Y)es, (N)o, (R)efresh : ");  
                    while (dwResult == 0)  
                    {  
                        switch (toupper(getwchar()))  
                        {  
                        case 'Y':  
                            dwResult = IDYES;  // Close apps  
                            break;  
                        case 'N':  
                            dwResult = IDNO;  
                            break;  
                        case 'R':  
                            dwResult = IDRETRY;  
                            break;  
                        }  
                    }  
                    printf("\n");  
                    break;  
                }  
            default:  
                break;  
            }  
            printf("  response: %d\n  ", dwResult);  
            return dwResult;  
        }  
    };  
  
    ```  
  
-   진행률 데이터는 0\(0%\)에서 255\(100%\) 사이의 부호 없는 `char`입니다.  
  
    ```cpp  
    private: // IProgressObserver  
        virtual void OnProgress(unsigned char ubProgressSoFar)  
        {…………  
       }  
  
    ```  
  
-   결과는 `Finished` 메서드에 전달됩니다.  
  
    ```cpp  
    virtual void Finished(HRESULT hr)  
    {  
    // This HRESULT is communicated over MMIO and may be different than process  
    // Exit code of the Chainee Setup.exe itself  
    printf("\r\nFinished HRESULT: 0x%08X\r\n", hr);  
    }  
  
    ```  
  
    > [!IMPORTANT]
    >  [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 재배포 가능 패키지에서는 일반적으로 많은 진행률 메시지와 체이너 측 완료를 나타내는 단일 메시지를 기록합니다.  또한 `Abort` 레코드를 찾아서 비동기적으로 읽습니다.  `Abort` 레코드를 수신하는 경우 설치를 취소하고 설치가 중단되고 설정 작업이 롤백된 후 데이터로 E\_ABORT를 사용하여 완성된 레코드를 기록합니다.  
  
 일반적인 서버에서는 임의의 MMIO 파일 이름을 만들어 `Server::CreateSection`의 이전 코드 예제에 나온 것과 같은 파일을 만든 다음 `CreateProcess` 메서드를 사용하여 재배포 가능 패키지를 시작하여 파이프 이름을 `-pipe someFileSectionName` 옵션으로 전달합니다.  서버는 응용 프로그램 UI 고유 코드를 사용하여 `OnProgress`, `Send` 및 `Finished` 메서드를 구현해야 합니다.  
  
## 참고 항목  
 [개발자를 위한 배포 가이드](../../../docs/framework/deployment/deployment-guide-for-developers.md)   
 [배포](../../../docs/framework/deployment/net-framework-and-applications.md)