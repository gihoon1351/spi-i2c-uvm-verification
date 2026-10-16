# 시뮬레이션 및 보드 검증 안내

## VCS UVM

라이선스가 있는 Synopsys VCS, UVM 1.2와 make가 준비된 Linux 환경을 사용합니다. 원본 Makefile의 상대경로를 보존했습니다.

```sh
cd spi
make TEST=spi_full_cov_test SEED=1
```

```sh
cd i2c
make TEST=i2c_random_test SEED=1
```

각 명령은 해당 폴더에서 실행합니다. Makefile에는 코드 커버리지 옵션도 있으며, 코드 커버리지와 UVM 기능 커버리지는 구분합니다. 재실행 시 UVM 오류 수, Scoreboard 비교 수, 시드와 커버리지를 함께 기록하세요.

## 보드용 RTL

`board/`는 두 보드 통신용 제출 소스입니다. UVM DUT와 보드용 top은 목적이 다르므로 폴더 전체를 하나의 DUT로 중복 컴파일하지 않습니다. 보드 연결에서는 SCLK/MOSI/MISO/SS_n 또는 SCL/SDA와 접지·풀업 조건을 확인합니다.

이번 정리에서는 VCS 및 보드 검증을 재실행하지 않았습니다.
