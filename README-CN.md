[English](./README.md) | 中文

<h1 align="center">TRON-PHP</h1>

<p align="center">
  <a href="https://github.com/xiaohuasheng0x1/tron-php/releases"><img src="https://poser.pugx.org/xiaohuasheng0x1/tron-php/v/stable" alt="Stable Version"></a>
  <a href="https://www.php.net"><img src="https://img.shields.io/badge/php-%3E=7.2-brightgreen.svg?maxAge=2592000" alt="Php Version"></a>
  <a href="https://github.com/xiaohuasheng0x1/tron-php/blob/master/LICENSE"><img src="https://img.shields.io/github/license/xiaohuasheng0x1/tron-php.svg?maxAge=2592000" alt="tron-php License"></a>
  <a href="https://packagist.org/packages/xiaohuasheng0x1/tron-php"><img src="https://poser.pugx.org/xiaohuasheng0x1/tron-php/downloads" alt="Total Downloads"></a>
</p>

## 概述

TRON-PHP 目前支持波场的 TRX 和 TRC20 中常用生成地址，发起转账，离线签名等功能。

## 特点

1. 一套写法兼容 TRON 网络中 TRX 货币和 TRC 系列所有通证
1. 接口方法可可灵活增减

## 支持方法

- 生成地址 `generateAddress()`
- 验证地址 `validateAddress(Address $address)`
- 根据私钥得到地址 `privateKeyToAddress(string $privateKeyHex)`
- 查询余额 `balance(Address $address)`
- 交易转账(离线签名) `transfer(Address $from, Address $to, float $amount)`
- 查询最新区块 `blockNumber()`
- 根据区块链查询信息 `blockByNumber(int $blockID)`
- 根据交易哈希查询信息 `transactionReceipt(string $txHash)`

## 快速开始

### 安装

PHP8
``` php
composer require xiaohuasheng0x1/tron-php
```

or PHP7
``` php
composer require xiaohuasheng0x1/tron-php ~1.3
```

### 接口调用

``` php
use GuzzleHttp\Client;

$uri = 'https://api.trongrid.io';// mainnet
// $uri = 'https://api.shasta.trongrid.io';// shasta testnet
$api = new \Tron\Api(new Client(['base_uri' => $uri]));

$trxWallet = new \Tron\TRX($api);
$addressData = $trxWallet->generateAddress();
// $addressData->privateKey
// $addressData->address

$config = [
    'contract_address' => 'TR7NHqjeKQxGTCi8q8ZY4pL8otSzgjLj6t',// USDT TRC20
    'decimals' => 6,
];
$trc20Wallet = new \Tron\TRC20($api, $config);
$addressData = $trc20Wallet->generateAddress();
```

## 计划

- 支持 TRC10
- 智能合约

## 扩展包

| 扩展包名 | 描述 | 应用场景 |
| :-----| :---- | :---- |
| [xiaohuasheng0x1/tron-api](https://github.com/xiaohuasheng0x1/tron-api) | 波场官方文档推荐 PHP 扩展包 | 波场基础Api |

## 🌟🌟

[![Stargazers over time](https://starchart.cc/xiaohuasheng0x1/tron-php.svg)](https://starchart.cc/xiaohuasheng0x1/tron-php)

## 合作

联系方式
- WX：zgf243944672
- QQ：243944672
