> [!NOTE]
> `dotnet build` 및 `dotnet run` 등 복원 발생이 필요한 모든 명령에 의해 암시적으로 실행되기 때문에 .NET Core 2.0부터 [`dotnet restore`](~/docs/core/tools/dotnet-restore.md)를 실행할 필요가 없습니다. [Visual Studio Team Services의 지속적인 통합 빌드](/vsts/build-release/apps/aspnet/build-aspnet-core)와 같이 명시적 복원을 수행하는 것이 올바른 특정 시나리오 또는 복원이 발생하는 시간을 명시적으로 제어해야 하는 빌드 시스템에서는 여전히 유효한 명령입니다.
>
> 또한 이 명령은 긴 형식(예: `--source`)으로 전달될 때 `dotnet restore` 옵션도 지원합니다. `-s`와 같이 짧은 형식의 옵션은 지원되지 않습니다.