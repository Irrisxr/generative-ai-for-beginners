# Setup Your Dev Environment

Мы настраиваем этот репозиторий и курс с помощью [контейнера разработки](https://containers.dev?WT.mc_id=academic-105485-koreyst), который имеет универсальную среду выполнения, поддерживающую разработку на Python3, .NET, Node.js и Java. Соответствующая конфигурация определена в файле `devcontainer.json`, расположенном в папке `.devcontainer/` в корне этого репозитория.

Чтобы активировать dev-контейнер, запустите его в [GitHub Codespaces](https://docs.github.com/en/codespaces/overview?WT.mc_id=academic-105485-koreyst) (для облачной среды исполнения) или в [Docker Desktop](https://docs.docker.com/desktop/?WT.mc_id=academic-105485-koreyst) (для локальной среды исполнения, размещенной на устройстве). Прочитайте [эту документацию](https://code.visualstudio.com/docs/devcontainers/containers?WT.mc_id=academic-105485-koreyst) для получения более подробной информации о работе dev-контейнеров в VS Code.  

> [!TIP] 
> Мы рекомендуем использовать GitHub Codespaces для быстрого старта с минимальными усилиями. Он предоставляет щедрую [квоту бесплатного использования](https://docs.github.com/billing/managing-billing-for-github-codespaces/about-billing-for-github-codespaces#monthly-included-storage-and-core-hours-for-personal-accounts?WT.mc_id=academic-105485-koreyst) для личных аккаунтов. Настройте [таймауты](https://docs.github.com/codespaces/setting-your-user-preferences/setting-your-timeout-period-for-github-codespaces?WT.mc_id=academic-105485-koreyst) для остановки или удаления неактивных кодовых пространств, чтобы максимально использовать квоту.


## 1. Выполнение заданий

В каждом уроке будут _опциональные_ задания, которые могут быть представлены на одном или нескольких языках программирования, включая: Python, .NET/C#, Java и JavaScript/TypeScript. В этом разделе приведены общие рекомендации по выполнению этих заданий.

### 1.1 Задания на языке Python

Задания на языке Python предоставляются либо в виде приложений (файлы `.py`), либо в виде блокнотов Jupyter (файлы `.ipynb`). 
- Чтобы запустить блокнот, откройте его в Visual Studio Code, затем нажмите _Select Kernel_ (справаa вверху) и выберите Python 3, показанный по умолчанию. Теперь вы можете _Запустить все_, чтобы запустить блокнот.
- Чтобы запустить Python-приложения из командной строки, следуйте инструкциям по конкретным заданиям, чтобы убедиться, что вы выбрали правильные файлы и указали необходимые аргументы

## 2. Настройка провайдеров

Задания **могут** также быть настроены для работы с одной или несколькими развернутыми большими языковыми моделями (LLM) через поддерживаемых поставщиков услуг, таких как OpenAI, Azure или Hugging Face. Они предоставляют _хостинговую конечную точку_ (API), к которой мы можем получить программный доступ с помощью правильных учетных данных (API-ключа или токена). В этом курсе мы рассмотрим таких провайдеров:

 - [OpenAI](https://platform.openai.com/docs/models?WT.mc_id=academic-105485-koreyst) с различными моделями, включая основную серию GPT.
 - [Azure OpenAI](https://learn.microsoft.com/azure/ai-services/openai/?WT.mc_id=academic-105485-koreyst) для моделей OpenAI, ориентированных на корпоративное использование.
 - [Hugging Face](https://huggingface.co/docs/hub/index?WT.mc_id=academic-105485-koreyst) для моделей с открытым исходным кодом и сервера выводов.

**Для выполнения этих заданий вам потребуется использовать собственные учетные записи**. Задания не являются обязательными, поэтому вы можете выбрать одного, всех или ни одного из провайдеров в зависимости от ваших интересов. Некоторые рекомендации по регистрации:

| Регистрация | Стоимость | API-ключ | Игровая площадка | Комментарии |
|:---|:---|:---|:---|:---|
| [OpenAI](https://platform.openai.com/signup?WT.mc_id=academic-105485-koreyst)| [Pricing](https://openai.com/pricing#language-models?WT.mc_id=academic-105485-koreyst)| [Project-based](https://platform.openai.com/api-keys?WT.mc_id=academic-105485-koreyst) | [No-Code, Web](https://platform.openai.com/playground?WT.mc_id=academic-105485-koreyst) | Доступно несколько моделей |
| [Azure](https://aka.ms/azure/free?WT.mc_id=academic-105485-koreyst)| [Pricing](https://azure.microsoft.com/pricing/details/cognitive-services/openai-service/?WT.mc_id=academic-105485-koreyst)| [SDK Quickstart](https://learn.microsoft.com/azure/ai-services/openai/quickstart?WT.mc_id=academic-105485-koreyst)| [Studio Quickstart](https://learn.microsoft.com/azure/ai-services/openai/quickstart?WT.mc_id=academic-105485-koreyst) | [Must Apply Ahead For Access](https://learn.microsoft.com/azure/ai-services/openai/?WT.mc_id=academic-105485-koreyst)|
| [Hugging Face](https://huggingface.co/join?WT.mc_id=academic-105485-koreyst) | [Pricing](https://huggingface.co/pricing) | [Access Tokens](https://huggingface.co/docs/hub/security-tokens?WT.mc_id=academic-105485-koreyst) | [Hugging Chat](https://huggingface.co/chat/?WT.mc_id=academic-105485-koreyst)| [Hugging Chat has limited models](https://huggingface.co/chat/models?WT.mc_id=academic-105485-koreyst)|
| | | | | |

Следуйте приведенным ниже инструкциям, чтобы _конфигурировать_ это хранилище для использования с различными провайдерами. Задания, требующие определенного провайдера, будут содержать один из этих тегов в имени файла:
 - `aoai` - требуется конечная точка Azure OpenAI, ключ
 - `oai` - требуется конечная точка OpenAI, ключ
 - `hf` - требуется токен Hugging Face


Переведено с помощью DeepL.com (бесплатная версия)

Вы можете настроить одного, ни одного или всех провайдеров. Связанные задания будут просто ошибаться при отсутствии учетных данных.

### 2.1. Создание файла `.env`

Мы предполагаем, что вы уже прочитали руководство выше и зарегистрировались у соответствующего провайдера, а также получили необходимые учетные данные для аутентификации (API_KEY или токен). В случае с Azure OpenAI мы предполагаем, что у вас также есть действующее развертывание службы Azure OpenAI (конечная точка) с как минимум одной моделью GPT, развернутой для завершения чата.

Следующим шагом будет настройка ваших **локальных переменных окружения** следующим образом:


1. Найдите в корневой папке файл `.env.copy`, который должен иметь следующее содержание:

   ``bash
   # OpenAI Provider
   OPENAI_API_KEY='<добавьте сюда ваш ключ API OpenAI>'

   ## Azure OpenAI
   AZURE_OPENAI_API_VERSION='2024-02-01' # По умолчанию установлено!
   AZURE_OPENAI_API_KEY='<добавьте сюда ваш ключ AOAI>'
   AZURE_OPENAI_ENDPOINT='<добавьте сюда конечную точку вашего сервиса AOIA>'
   AZURE_OPENAI_DEPLOYMENT='<добавьте сюда название модели завершения чата>' 
   AZURE_OPENAI_EMBEDDINGS_DEPLOYMENT='<добавьте сюда название вашей модели встраивания>'

   ## Обнимающееся лицо
   HUGGING_FACE_API_KEY='<добавьте сюда свой API или токен HuggingFace>'
   ```

2. Скопируйте этот файл в `.env` с помощью команды ниже. Этот файл является _gitignore-d_, сохраняя секреты в безопасности.

   ``bash
   cp .env.copy .env
   ```

3. Заполните значения (замените заполнители справа от `=`), как описано в следующем разделе.

3. (Опция) Если вы используете GitHub Codespaces, у вас есть возможность сохранить переменные окружения как _Codespaces secrets_, связанные с этим репозиторием. В этом случае вам не нужно будет настраивать локальный файл .env. **Однако обратите внимание, что эта опция работает только при использовании GitHub Codespaces.** Вам все равно придется настраивать .env-файл, если вместо этого вы используете Docker Desktop.


### 2.2. Заполнение файла `.env`

Давайте посмотрим на имена переменных, чтобы понять, что они собой представляют:

| Переменная | Описание |
| :--- | :--- |
| HUGGING_FACE_API_KEY | Это токен доступа пользователя, который вы установили в своем профиле |
| OPENAI_API_KEY | Это ключ авторизации для использования сервиса для конечных точек, не относящихся к Azure OpenAI |
| AZURE_OPENAI_API_KEY | Это ключ авторизации для использования данного сервиса |
| AZURE_OPENAI_ENDPOINT | Это развернутая конечная точка для ресурса Azure OpenAI |
| AZURE_OPENAI_DEPLOYMENT | Это конечная точка развертывания модели _генерации текста_ |
| | AZURE_OPENAI_EMBEDDINGS_DEPLOYMENT | Это конечная точка развертывания модели _встраивания текста_ |
| | |

Примечание: Последние две переменные Azure OpenAI отражают модель по умолчанию для завершения чата (генерация текста) и векторного поиска (вкрапления) соответственно. Инструкции по их настройке будут описаны в соответствующих заданиях.


### 2.3 Настройка Azure: С портала

Конечная точка Azure OpenAI и ключевые значения будут найдены на [Azure Portal](https://portal.azure.com?WT.mc_id=academic-105485-koreyst), поэтому начнем с него.

1. Перейдите на [Azure Portal](https://portal.azure.com?WT.mc_id=academic-105485-koreyst)
1. Щелкните опцию **Keys and Endpoint** в боковой панели (меню слева).
1. Нажмите **Показать ключи** - вы должны увидеть следующее: KEY 1, KEY 2 и Endpoint.
1. Используйте значение KEY 1 для AZURE_OPENAI_API_KEY
1. Используйте значение Endpoint для AZURE_OPENAI_ENDPOINT

Далее нам нужны конечные точки для конкретных моделей, которые мы развернули.

1. Нажмите на опцию **Model deployments** в боковой панели (левое меню) для ресурса Azure OpenAI.
1. На целевой странице нажмите **Управление развертываниями**.

Это приведет вас на сайт Azure OpenAI Studio, где мы найдем другие значения, как описано ниже.

### 2.4 Настройка Azure: Из студии

1. Перейдите на сайт [Azure OpenAI Studio](https://oai.azure.com?WT.mc_id=academic-105485-koreyst) **с вашего ресурса**, как описано выше.
1. Перейдите на вкладку **Развертывания** (боковая панель, слева), чтобы просмотреть развернутые в данный момент модели.
1. Если нужная вам модель не развернута, используйте **Создать новое развертывание** для ее развертывания.
1. Вам понадобится модель _текстовой генерации_ - мы рекомендуем: **gpt-35-turbo**.
1. Вам понадобится модель _текстовой вставки_ - мы рекомендуем **text-embedding-ada-002**.

Теперь обновите переменные окружения, чтобы отразить используемое имя _развертывания_. Как правило, оно совпадает с именем модели, если вы не изменили его явно. Так, например, у вас может быть:

``bash
AZURE_OPENAI_DEPLOYMENT='gpt-35-turbo'
AZURE_OPENAI_EMBEDDINGS_DEPLOYMENT='text-embedding-ada-002'
```

**Не забудьте сохранить файл .env после завершения работы**. Теперь вы можете выйти из файла и вернуться к инструкциям по запуску блокнота.

### 2.5 Настройка OpenAI: из профиля

Ваш API-ключ OpenAI можно найти в вашей [учетной записи OpenAI](https://platform.openai.com/api-keys?WT.mc_id=academic-105485-koreyst). Если у вас его нет, вы можете зарегистрировать аккаунт и создать API-ключ. Как только вы получите ключ, вы можете использовать его для заполнения переменной `OPENAI_API_KEY` в файле `.env`.

### 2.6 Настройте обнимающееся лицо: Из профиля

Ваш токен Hugging Face можно найти в вашем профиле в разделе [Токены доступа](https://huggingface.co/settings/tokens?WT.mc_id=academic-105485-koreyst). Не публикуйте и не делитесь ими публично. Вместо этого создайте новый токен для использования в этом проекте и скопируйте его в файл `.env` в переменную `HUGGING_FACE_API_KEY`. Примечание:_ Технически это не API-ключ, но он используется для аутентификации, поэтому мы сохраняем это соглашение об именовании для согласованности.

