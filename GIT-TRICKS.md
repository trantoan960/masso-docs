# Các thủ thuật trong quá trình làm việc với GIT

Trong quá trình làm việc dự án, sẽ xuất hiện nhưng lỗi rất lặt vặt, thậm chí là quên không commit, không push code, pull nhánh này trước nhánh kia,... Trong quá trình thực hiện có một số những quy định cũng như thủ thuật mà nên biết để sử dụng một cách tốt nhất.

## Example Git flow

Flow tham khảo: [A successful Git branching model](http://nvie.com/posts/a-successful-git-branching-model/)

### Giả định
* Đã tạo Central Repository (Nguồn trung tâm) trên Github（hoặc Bitbucket）.
* Branch mặc định của Central Repository là master.
* Lập trình viên có thể  fork (tạo nhánh) đối với Central Repository.
* Đã quyết định người review và người có quyền merge.

### Nguyên tắc
* Mỗi pull-request tương ứng với một ticket.
* Mỗi một pull-request không hạn chế số lượng commit
* Pull-request title phải đặt sao cho tương ứng với title của task với format `refs [Loại ticket] #[Số ticket] [Nội dung ticket]` （Ví dụ: `refs bug #1234 Sửa lỗi cache`）.
* Đối với commit title, trong trường hợp pull-request đó chỉ có 1 commit thì có thể đặt commit title tương tự như trên là `refs [Loại ticket] #[Số ticket] [Nội dung ticket]` （Ví dụ: `refs bug #1234 Sửa lỗi cache`）.\
  Tuy nhiên với trường hợp 1 ppull-request có chứa nhiêù commit thì cần phải ghi rõ trong nội dung commit title là trong commit đó xử lý đối ứng vấn đề gì.
    * Ví dụ:
        1. Pull-request title: `refs bug #1234 Sửa lỗi cache`
        2. Trong trường hợp pull-request có 2 commit thì nội dung commit title của 2 commit sẽ tương ứng như sau
            * `Tạo method thực hiện việc clear cache trong Model`
            * `Tại controller gọi method ở Model để thực hiện việc clear cache`
* Gitflow đến thời điểm 2018/03/28 có quy định là 1 pull-request chỉ một commit sẽ không còn hiệu lực nữa. Tuy nhiên với các dự án mà teamsize lớn hơn 10 người thì để nhằm mục đích cho thuận tiện cho việc confirm thì khuyến khích dùng squash and merge .
* Ngoài ra thì với gitflow trước đây ( trước thời điểm 2018/03/28) thì có cho phép dùng force push, tuy nhiên do khi sử dụng force push sẽ xoá hết lịch sử thay đổi do vậy gitlow hiện tại không khuyến khích sử dụng force push. Trong trường hợp cần sử dụng force push thì cần có sự đồng thuận từ team.
* Tại môi trường local(trên máy lập trình viên), tuyệt đối không được thay đổi code khi ở branch master.Nhất định phải thao tác trên branch khởi tạo để làm task.

### Chuẩn bị

1. Trên Github (Bitbucket), fork Central Repository về tài khoản của mình（repository ở tài khoản của mình sẽ được gọi là Forked Repository）.

2. Clone (tạo bản sao) Forked Repository ở môi trường local.Tại thời điểm này, Forked Repository sẽ được tự động đăng ký dưới tên là `origin`.
    ```sh
    $ git clone [URL của Forked Repository]
    ```

3. Truy cập vào thư mục đã được tạo ra sau khi clone, đăng ký Central Repository dưới tên `upstream`.
    ```sh
    $ cd [thư mục được tạo ra]
    $ git remote add upstream [URL của Central Repository]
    ```

### Quy trình

Từ đây, Central Repository và Forked Repository sẽ được gọi lần lượt là `upstream` và `origin`.

1. Đồng bộ hóa branch master tại local với upstream.
    ```sh
    $ git checkout master
    $ git pull upstream master
    ```

2. Tạo branch để làm task từ branch master ở local. Tên branch là số ticket của task（Ví dụ: `task/1234`）.
    ```sh
    $ git checkout master # <--- Không cần thiết nếu đang ở trên branch master
    $ git checkout -b task/1234
    ```

3. Tiến hành làm task（Có thể commit bao nhiêu tùy ý）.

4. Push code lên origin.

    ```sh
    $ git push origin task/1234
    ```

5. Tại origin trên Github（Bitbucket）、từ branch `task/1234` đã được push lên hãy gửi pull-request đối với branch master của upstream.

6. Hãy gửi link URL của trang pull-request cho reviewer trên chatwork để tiến hành review code.

    6.1. Trong trường hợp reviewer có yêu cầu sửa chữa, hãy thực hiện các bước 3. 〜 5..
    6.2. Tiếp tục gửi lại URL cho reviewer trên chatwork để tiến hành việc review code.

7. Nếu trên 2 người reviewer đồng ý với pull-request, người reviewer cuối cùng sẽ thực hiện việc merge pull-request.
   Revewer xác nhận sự đồng ý bằng comment LGTM.
   
8. Quay trở lại 1.


### Đối với dự án áp dụng quy định tương ứng với 1 pull-request chỉ cho phép 1 commit

Từ đây, Central Repository và Forked Repository sẽ được gọi lần lượt là `upstream` và `origin`.

1. Đồng bộ hóa branch master tại local với upstream.
    ```sh
    $ git checkout master
    $ git pull upstream master
    ```

2. Tạo branch để làm task từ branch master ở local. Tên branch là số ticket của task（Ví dụ: `task/1234`）.
    ```sh
    $ git checkout master # <--- Không cần thiết nếu đang ở trên branch master
    $ git checkout -b task/1234
    ```

3. Tiến hành làm task（Có thể commit bao nhiêu tùy ý）.

4. Trường hợp đã tạo nhiều commit trong quá trình làm task、tại 5. trước khi push phải dùng rebase -i để hợp các commit lại thành 1 commit duy nhất.
    ```sh
    $ git rebase -i [Giá trị hash của commit trước commit đầu tiên trong quá trình làm task]
    ```

5. Quay trở về branch master ở local và lấy code mới nhất về

    ```sh
    $ git checkout master
    $ git pull upstream master
    ```

6. Quay trở lại branch làm task, sau đó rebase với branch master.

    ```sh
    $ git checkout task/1234
    $ git rebase master
    ```
    **Trường hợp xảy ra conflict trong quá trình rebase、hãy thực hiện các thao tác của mục「Khi xảy ra conflict trong quá trình rebase」.**

7. Push code lên origin.

    ```sh
    $ git push origin task/1234
    ```

8. Tại origin trên Github（Bitbucket）、từ branch `task/1234` đã được push lên hãy gửi pull-request đối với branch master của upstream.

9. Hãy gửi link URL của trang pull-request cho reviewer trên chatwork để tiến hành review code.

    9.1. Trong trường hợp reviewer có yêu cầu sửa chữa, hãy thực hiện các bước 3. 〜 6.

    9.2 push -f (push đè hoàn toàn lên code cũ) đối với remote branch làm task.
    ```sh
    $ git push origin task/1234 -f
    ```

    9.3 Tiếp tục gửi lại URL cho reviewer trên chatwork để tiến hành việc review code.

10. Nếu trên 2 người reviewer đồng ý với pull-request, người reviewer cuối cùng sẽ thực hiện việc merge pull-request.
    Revewer xác nhận sự đồng ý bằng comment LGTM.

11. Quay trở lại 1.

#### Khi xảy ra conflict trong quá trình rebase

Khi xảy ra conflict trong quá trình rebase, sẽ có hiển thị như dưới đây (tại thời điểm này sẽ bị tự động chuyển về một branch vô danh)
```sh
$ git rebase master
First, rewinding head to replay your work on top of it...
Applying: refs #1234 Sửa lỗi cache
Using index info to reconstruct a base tree...
Falling back to patching base and 3-way merge...
Auto-merging path/to/conflicting/file
CONFLICT (add/add): Merge conflict in path/to/conflicting/file
Failed to merge in the changes.
Patch failed at 0001 refs #1234 Sửa lỗi cache
The copy of the patch that failed is found in:
    /path/to/working/dir/.git/rebase-apply/patch

When you have resolved this problem, run "git rebase --continue".
If you prefer to skip this patch, run "git rebase --skip" instead.
To check out the original branch and stop rebasing, run "git rebase --abort".
```

1. Hãy thực hiện fix lỗi conflict thủ công（những phần được bao bởi <<< và >>> ）.
Trong trường hợp muốn dừng việc rebase lại, hãy dùng lệnh `git rebase --abort`.

2. Khi đã giải quyết được tất cả các conflict, tiếp tục thực hiện việc rebase bằng:

    ```sh
    $ git add .
    $ git rebase --continue
    ```

## Quy định commit khi làm việc với Git

Nhiều người vẫn nghĩ việc commit vô cùng dễ dàng chỉ cần gõ và nghĩ ra một cái tên là đủ. Nhưng nếu để quản lý lại một đống commit mà bạn đã làm trước đó thì vô cùng khó khăn. Hãy hình dung như thế này. Mình muốn biết được 13:00 01/10/2018 bạn đã commit bao nhiêu lần, mỗi commit thực hiện phần gì chi tiết ở file nào. mà chỉ cần nhìn ở commit không cần vào nội dung của file. Bạn thấy gặp vấn đề rồi chứ 😁😁

> Bên dưới là một nguyên bản quy định các commit vô cùng chặt chẽ từ Angular - framework nổi tiếng Javascript. Nếu bạn đọc kỹ sẽ thấy có những quy định giúp bạn định danh được vùng hoạt động trong project của bạn, điều này giúp bạn có một logic code tốt hơn rất nhiều. **Một số nội dung bên dưới mình đã chỉnh sửa, hoặc cắt đi để nó phù hợp với các dự án ban đầu bạn tiếp xúc tại công ty. Điều này có nghĩa rằng, sau này sẽ có những quy định khác tùy vào lead nơi bạn làm việc hoặc chi tiết hơn là tại công ty MASSO**

We have very precise rules over how our git commit messages can be formatted.  This leads to **more
readable messages** that are easy to follow when looking through the **project history**.  But also,
we use the git commit messages to **generate the Project change log**.

### Commit Message Format
Each commit message consists of a **header**, a **body** and a **footer**.  The header has a special
format that includes a **type**, a **scope** and a **subject**:

```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

The **header** is mandatory and the **scope** of the header is optional.

Any line of the commit message cannot be longer 100 characters! This allows the message to be easier
to read on GitHub as well as in various git tools.

The footer should contain a [closing reference to an issue](https://help.github.com/articles/closing-issues-via-commit-messages/) if any.

Samples:

```
docs(changelog): update changelog to beta.5
```
```
fix(release): need to depend on latest rxjs and zone.js

The version in our package.json gets copied to the one we publish, and users need the latest of these.
```

### Revert
If the commit reverts a previous commit, it should begin with `revert: `, followed by the header of the reverted commit. In the body it should say: `This reverts commit <hash>.`, where the hash is the SHA of the commit being reverted.

### Type
Must be one of the following:

* **build**: Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm)
* **ci**: Changes to our CI configuration files and scripts (example scopes: Circle, BrowserStack, SauceLabs)
* **docs**: Documentation only changes
* **feat**: A new feature
* **fix**: A bug fix
* **perf**: A code change that improves performance
* **refactor**: A code change that neither fixes a bug nor adds a feature
* **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
* **test**: Adding missing tests or correcting existing tests

### Scope
The scope should be the name of the npm package affected (as perceived by the person reading the changelog generated from commit messages).

The following is the list of supported scopes:

* **animations**
* **common**
* **compiler**
* **compiler-cli**
* **core**
* **elements**
* **forms**
* **http**
* **language-service**
* **platform-browser**
* **platform-browser-dynamic**
* **platform-server**
* **platform-webworker**
* **platform-webworker-dynamic**
* **router**
* **service-worker**
* **upgrade**
* **zone.js**

There are currently a few exceptions to the "use package name" rule:

* **packaging**: used for changes that change the npm package layout in all of our packages, e.g.
  public path changes, package.json changes done to all packages, d.ts file/format changes, changes
  to bundles, etc.
* **changelog**: used for updating the release notes in CHANGELOG.md
* none/empty string: useful for `style`, `test` and `refactor` changes that are done across all
  packages (e.g. `style: add missing semicolons`) and for docs changes that are not related to a
  specific package (e.g. `docs: fix typo in tutorial`).

### Subject
The subject contains a succinct description of the change:

* use the imperative, present tense: "change" not "changed" nor "changes"
* don't capitalize the first letter
* no dot (.) at the end

### Body
Just as in the **subject**, use the imperative, present tense: "change" not "changed" nor "changes".
The body should include the motivation for the change and contrast this with previous behavior.

### Footer
The footer should contain any information about **Breaking Changes** and is also the place to
reference GitHub issues that this commit **Closes**.

**Breaking Changes** should start with the word `BREAKING CHANGE:` with a space or two newlines. The rest of the commit message is then used for this.

