# Исправление ошибки [remote rejected]

Если Git при попытке `push` выдает ошибку:

`! [remote rejected] main -> main (permission denied)`

или

`! [remote rejected] <branch_name> -> <branch_name> (permission denied)`

это означает ошибку в конфигурации программы Git на компьютере. В этом случае используем следующую инструкцию:

1. Открываем для редактирования глобальный config для экземпляра Git, установленного на компьютер

    `git config --global --edit`

2. Добавляем необходимые разрешения:

        [credential]
            helper = <Nickname>
            useHttpPath = true

3. Закрываем файл

4. Вновь выполняем `push`

5. Проходим авторизацию на GitHub