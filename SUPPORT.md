# Do MTP Support / 지원

Do MTP (formerly Naru) lets you access an Android phone in macOS Finder over USB.

## Contact / 문의
[Open a support request](https://github.com/hamasang/Naru/issues/new) or [view existing issues](https://github.com/hamasang/Naru/issues).
Maintainer: [hamasang](https://github.com/hamasang). A GitHub account is needed to post an issue; reading this page does not require an account.
Please include your macOS version, Mac chip, Android model/version, app version, exact error and steps to reproduce. Issues are public: do not include private files, passwords, serial numbers or unredacted logs/screenshots.

## Getting started
1. Use macOS 15.4 or later and a USB cable that supports data transfer.
2. Install and launch Do MTP. It lives in the menu bar, not a separate main window.
3. Enable Do MTP in **System Settings → General → Login Items & Extensions → File System Extensions**.
4. Close other MTP transfer apps. Connect your Android phone, unlock it and select **File transfer** in its USB options. USB debugging is not needed.
5. Choose **Open in Finder** from Do MTP. If automatic mounting is off, choose **Mount** first.
6. On first use, select the phone volume in **Open Your Phone in Finder** and click **Allow**. Do not select your Mac home folder.
7. Browse the phone under Finder **Locations** and copy files between the phone and Mac. Test changes with disposable files first.
8. Wait for transfers to finish, then **Eject** before unplugging.

## Troubleshooting
- **No phone / empty storage:** unlock it, select File transfer, and try another data cable or USB port.
- **Extension disabled:** enable it in System Settings, then use Check Extension Status Again.
- **Access denied:** choose Open in Finder again and authorize the phone volume in the macOS picker.
- **Mount or transfer timeout:** finish or cancel current transfers, reconnect the phone and try Mount. Quit competing MTP apps.
- **Different storage layout:** one storage appears at the volume root; multiple storages appear as separate folders.
Compatibility can vary by Android device. This is not an iPhone transfer app.

## 한국어 사용 안내
1. macOS 15.4 이상과 데이터 전송용 USB 케이블을 준비합니다.
2. Do MTP를 실행합니다. 별도 메인 창 없이 메뉴 막대에 표시됩니다.
3. **시스템 설정 → 일반 → 로그인 항목 및 확장 프로그램 → 파일 시스템 확장**에서 Do MTP를 켭니다.
4. 다른 MTP 전송 앱을 종료하고 휴대폰을 연결합니다. 잠금을 해제한 뒤 USB 모드를 **파일 전송**으로 선택합니다. USB 디버깅은 필요하지 않습니다.
5. 메뉴에서 **Finder에서 열기**를 선택합니다. 자동 마운트를 껐다면 먼저 **마운트**를 선택합니다.
6. 최초 승인 창에서 휴대폰 볼륨을 선택하고 **허용(Allow)**을 누릅니다.
7. Finder의 **위치**에서 휴대폰 파일을 탐색하고 양방향으로 복사합니다. 이름 변경이나 삭제는 테스트 파일로 먼저 확인하세요.
8. 전송이 끝나면 **추출(Eject)**한 뒤 케이블을 분리합니다.

문제가 있으면 [지원 요청](https://github.com/hamasang/Naru/issues/new)을 남겨 주세요. macOS·Android·앱 버전, Mac 칩, 휴대폰 모델, 재현 순서와 오류 문구를 적어 주세요. 공개 게시판이므로 개인 파일명·계정·일련번호는 가려 주세요.

[Privacy Policy / 개인정보 처리방침](PRIVACY.md)
