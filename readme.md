﻿Parallel Get
-------

*Parallel Get*
是一个用于MATLAB 平台，获取股票历史/即时行情数据的工具。

----
使用方法
=========
下载并添加至Path 即可直接调用函数。

----------

API 详解
====
**get_tick_data（code，date）**
获取个股以往某日历史的分笔数据明细。
示例1：
>\>\>get_tick_data('000002','2016-08-26')
>
    timestamp      price     change     volumns    amount  
    _________     ______     _______    _______    _______  
    '15:00:03'    '23.54'    '-0.03'    '19353'    '45557432'
    '14:57:00'    '23.57'    '--'       '1392'     '3280944'
    '14:56:57'    '23.57'    '--'       '263'      '619891'  
    '14:56:54'    '23.57'    '--'       '283'      '667031'  
    '14:56:51'    '23.57'    '--'       '218'      '513826'  
    '14:56:48'    '23.57'    '--'       '1428'     '3367681'
    '14:56:45'    '23.57'    '0.02'     '350'      '824950'

**get_hist_data(code)** 可以通过参数设置获取日k线、周k线、月k线，以及5分钟、15分钟、30分钟和60分钟k线数据。
获取单只股票日线数据
示例1：
>\>\>get_hist_data(000002,'d')
>
      date           open         high        close        low         volumne         p_change
      ________      ________    _______      ____       _______      _______        _________  
    '2016-08-23'    '24.390'    '25.280'    '24.700'    '23.830'    '1694763.25'     '0.000'
    '2016-08-24'    '24.400'    '24.840'    '23.990'    '23.750'    '1470675.62'     '-0.710'
    '2016-08-25'    '23.500'    '23.940'    '23.540'    '22.710'    '1821374.88'     '-0.450'
    '2016-08-26'    '23.590'    '23.590'    '22.890'    '22.880'    '1200024.12'     '-0.650'

**get_today_tick(code)**  获取单只股票今日tick数据（大约3s 更新一次）
示例1：
>\>\>get_today_tick(000002)
>
    timestamp      price
     ________       _____
    '14:02:54'    '22.92'
    '14:02:51'    '22.91'
    '14:02:48'    '22.92'
    '14:02:45'    '22.91'

示例2：
>\>\>  get_hist_data(300191,'15')
>
                timestamp          open       high       close       low       volumn      p_change
        _____________________    _______    _______    _______    _______    _________    ________
        '2016-09-26 15:00:00'    '37.5'     '37.53'    '37.28'    '37.15'    '6608.53'    '-0.22'
        '2016-09-26 14:45:00'    '37.5'     '37.63'    '37.5'     '37.28'    '6242.99'    '0",0,'
        '2016-09-26 14:30:00'    '37.8'     '37.9'     '37.61'    '37.61'    '2161'       '-0.19'
        '2016-09-26 14:15:00'    '37.8'     '37.89'    '37.83'    '37.73'    '1573.01'    '0.03'  
        '2016-09-26 14:00:00'    '37.78'    '37.9'     '37.8'     '37.74'    '1728.17'    '0.02'  
        '2016-09-26 13:45:00'    '37.76'    '37.8'     '37.78'    '37.52'    '3223.01'    '0.02'  
        '2016-09-26 13:30:00'    '37.95'    '37.97'    '37.77'    '37.75'    '1571'       '-0.18'
        '2016-09-26 13:15:00'    '37.88'    '37.95'    '37.95'    '37.68'    '1447'       '0.07'  

**get_realtime_quotes(code)** 获取多只股票当前时间的成交情况
示例1：
>\>\>get_realtime_quotes({'000002','000025'})
>
    code       name          open      pre_close     price        high        low         volumn          amount   
    ______      _______     _______     _______      _______      _______     _________    ________      ________
    '000002'    '万 科Ａ'    '25.190'    '25.480'     '24.680'    '25.350'    '24.400'    '132417339'    '3272364942'
    '000025'    '特 力Ａ'    '68.360'    '68.060'     '64.800'    '68.390'    '64.000'    '7135515'      '472024111'

----------
