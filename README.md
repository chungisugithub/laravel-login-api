<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/d/total.svg" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/v/stable.svg" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/license.svg" alt="License"></a>
</p>
## 주저리</br>
단순코딩의 대가 Belal Khan 선생님의 유튜브를 따라해 보았습니다.</br>
<a href="https://www.simplifiedcoding.net/laravel-rest-api-authentication/">Building Login API with OAuth2</a>
1. Introduction 2. Laravel Project 3. Configuring Git 4. Adding Passport 5. User Signup 6. User Login 7. User Logout 까지
정말 라라벨이 뭔지! 패스포트가 뭘해 주는건지 모른채 단지 동영상 수업 내용처럼 동작하는것에 초점을 맞추어 따라했습니다.
첫 번째 어려운 점은 버전 문제입니다. 라라벨의 버전이 7, 8, 9 등이 있어 문제가 발생하면, 버전을 의심해야 했습니다.
두 번째 난관은 컨트롤러의 리프레시토큰 코드가 추가되면서 POST 요청에 아무런 답이 없을때 입니다. 동영상 7번 까지는 삽질하면서 꾸역꾸역
따라잡았는데, 7번까지의 동영상에는 Laravel\Passport\Client를 사용하지 않았기에 깃허브의 소스코드를 보면서 왜 안될까????? 사실 제가 처음
역인것은 리프레시토큰 입니다. OAuth에 대한 동작을 실제 코드를 통해 이해 할려 시작했는데, 따라하면서 보니 억세스토큰만 보이고, 리프레시 토큰이
보이지 않아. 리프레시토큰을 확인해야겠다. 라는 생각으로 쉽게 포기가 되지 않았습니다.  Belal Khan 선생님이 동작이 안되는 코드를 올려 놓으시진 않았을 테니
버전 문제이거나, 환경에 문제가 있을거라 생각하고, 버전부터 laravel 7.30으로 바꾸어 다시 시작했어나 같은 문제에 봉착했습니다. 그러면 환경문제 다.
오류의 발생은 $request->user()가 NULL로 넘어오는 현상이 발생하고, 오류가 한번 발생하면, 앱을 재시작해야 되는 상황이 되었습니다. 그러다 구글검색에서
하나의 힌트를 얻었습니다. VSCode 사용시 아파치가 임베디드 상태에서 동작을 하게 되는데, 이때 싱글인스턴스로 동작을 한다는 것입니다. 하나의 Http 요청이 처리중에
또하나의 Http 요청을 하게되면, 문제가 발생하는 거지요. 먼저 요청한 프로세스를 나중에 요청한 프로세스에 의해 Kill되는 현상이 발생해서 응답이 없는 거지요. 해결방법은
물론 저의 경우 당장 리프레시토큰이 넘어 오는 것을 보기위한 방법이지요. 하나의 앱을 포트를 달리해 두개를 실행시켜 테스트해 리프레시 토큰을 보았습니다. 이제는 조금 더
삽질해서 XAMPP의 아파치 서버를 사용하니 정상동작하였습니다. 결론은 Belal Khan 선생님의 코드는 이상이 없고, 개발환경의 문제로 판명이 되었습니다. 이후 계속해서 동영상과
같이 Virtual Host도 사용해보고, Docker 환경도 테스트해보고 있습니다. 결과는 저는 만족스럽습니다. 만족감도 조금, Spring Security 환경과 조금 느낌은 다르지만, Laravel Passport가
익숙해지면 생산성이 아주 좋을것 같다는 생각입니다. 혹시나 누가 여기까지 오셨다면, 감사합니다. 좋은하루 되세요. 그리고 Belal Khan 선생님 Thank you very much. make your day..bye.

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains over 1500 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the Laravel [Patreon page](https://patreon.com/taylorotwell).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Cubet Techno Labs](https://cubettech.com)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[Many](https://www.many.co.uk)**
- **[Webdock, Fast VPS Hosting](https://www.webdock.io/en)**
- **[DevSquad](https://devsquad.com)**
- **[OP.GG](https://op.gg)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
