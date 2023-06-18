# VSD-TCL
# TCL WORKSHOP
- Create command and pass -csv from UNIX shell to TCL script
- Convert all inputs to format [1] and SDC format and pass to synthesis to Yosys
- Convert format [1] and SDC to format [2] and pass to timing tool 'Opentimer'
- Generate Output report

[DAY-1](#DAY-1)<br/>
[DAY-2](#DAY-2)<br/>
[DAY-3](#DAY-3)<br/>
[DAY-4](#DAY-4)<br/>


### DAY 1
Creating a TCL command
+ General Scenarios-From user point of view
  - Not providing .csv file as input
  - providing a .csv file which doesnt exist
  - Type "-help" to find out usage
  
![image](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/8d2619ff-6e42-43e1-9a4c-8b427da15875)

### DAY 2
Convert all inputs to format [1] and SDC format and pass to synthesis tool 'Yosys' 
- Creating Variables :
![prutha_day2_1](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/f10ada53-108b-49b1-8374-360d083c1282)
- Finding total rows and columns in given file :
![prutha_day2_2_2](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/0c3648d2-72ef-40de-8780-f29adf834f3b)
![prutha_day2_2_4](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/b80f1a3f-050f-4eb6-a818-b8bab5bc6f43)
![prutha_day3_!](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/b92d5d30-7b16-41d6-bc3d-8563cb4cb73d)

### DAY 3
**Input and Output Constraints Generation and bits/Bussed Differentiation**

![prutha_day3_2](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/ac057d49-58eb-4e43-8085-b6b4604b2134)
![day 3 and 4](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/b1993486-94a8-4732-89c8-969d45bf8166)

### DAY 4
- Introduction to Yosys synthesis tool usage

![day4_21](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/0572cded-4702-491b-a416-e9650c83b38d)

- Hierachy check and error handling script creation for yosys

![day4_23](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/e82b565d-56ee-48d2-a4cc-636997d605c7)
![day4_22](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/e9c4e6b7-225c-4698-a078-db703a7335c8)
![day4last1](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/f72950ec-6651-4f1d-88ff-91e40431486d)
![day4last](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/d50d51c4-0db1-4e8d-bfd5-2b5bdfd4d556)

### DAY 5
- Synthesis main file scripting and ouput file editing
  ![day5112](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/0b86d7c3-a4c5-4fa9-bbf0-f5eba6477724)
  ![day5_2](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/b1b573c4-58ae-4b96-b431-d8388034fdb7)

- error in executing Synthesis file
  ![day5_!!](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/3dce8e18-561e-4778-a8ff-dd75cd407a6e)

- Introduction to procs and demo of redirect stdout proc
  ![day_5_procs](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/02dd5608-97bb-4dd1-ba43-b63bbea4ae22)

- Timing analysis and config file generation
  ![day5_procs_ex](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/020a5ddb-c9d5-4808-a874-0ad05990d184)
  ![day_5conffile](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/6ce2bfdf-48db-4af0-af32-0daae25a8726)  
  ![day5_configfile](https://github.com/PruthaVernekar/VSD-TCL/assets/89785844/a015c3e7-50a4-4658-a90e-8678d4053638)

  - Output SDC Constraints to Opentimer format
     ```
        clock dco_clk 1500 50
        clock lfxt_clk 1600 40
        
        at dco_clk dco_clk dco_clk dco_clk dco_clk
        at lfxt_clk lfxt_clk lfxt_clk lfxt_clk lfxt_clk
        at cpu_en 100 101 102 103
        at dbg_en 101 102 103 104
        at dbg_i2c_addr_0_  102 103 104 105
        at dbg_i2c_addr_1_  102 103 104 105
        at dbg_i2c_addr_2_  102 103 104 105
        at dbg_i2c_addr_3_  102 103 104 105
        at dbg_i2c_addr_4_  102 103 104 105
        at dbg_i2c_addr_5_  102 103 104 105
        at dbg_i2c_addr_6_  102 103 104 105
        at dbg_i2c_broadcast_0_  103 104 105 106
        at dbg_i2c_broadcast_1_  103 104 105 106
        at dbg_i2c_broadcast_2_  103 104 105 106
        at dbg_i2c_broadcast_3_  103 104 105 106
        at dbg_i2c_broadcast_4_  103 104 105 106
        at dbg_i2c_broadcast_5_  103 104 105 106
        at dbg_i2c_broadcast_6_  103 104 105 106
        at dbg_i2c_scl 104 105 106 107
        at dbg_i2c_sda_in 105 106 107 108
        at dbg_uart_rxd 106 107 108 109
        at dmem_dout_0_  108 109 110 111
        at dmem_dout_10_  108 109 110 111
        at dmem_dout_11_  108 109 110 111
        at dmem_dout_12_  108 109 110 111
        at dmem_dout_13_  108 109 110 111
        at dmem_dout_14_  108 109 110 111
        at dmem_dout_15_  108 109 110 111
        at dmem_dout_1_  108 109 110 111
        at dmem_dout_2_  108 109 110 111
        at dmem_dout_3_  108 109 110 111
        at dmem_dout_4_  108 109 110 111
        at dmem_dout_5_  108 109 110 111
        at dmem_dout_6_  108 109 110 111
        at dmem_dout_7_  108 109 110 111
        at dmem_dout_8_  108 109 110 111
        at dmem_dout_9_  108 109 110 111
        at irq_0_  109 110 111 112
        at irq_10_  109 110 111 112
        at irq_11_  109 110 111 112
        at irq_12_  109 110 111 112
        at irq_13_  109 110 111 112
        at irq_1_  109 110 111 112
        at irq_2_  109 110 111 112
        at irq_3_  109 110 111 112
        at irq_4_  109 110 111 112
        at irq_5_  109 110 111 112
        at irq_6_  109 110 111 112
        at irq_7_  109 110 111 112
        at irq_8_  109 110 111 112
        at irq_9_  109 110 111 112
        at irq_acc_0_  109 110 111 112
        at irq_acc_10_  109 110 111 112
        at irq_acc_11_  109 110 111 112
        at irq_acc_12_  109 110 111 112
        at irq_acc_13_  109 110 111 112
        at irq_acc_1_  109 110 111 112
        at irq_acc_2_  109 110 111 112
        at irq_acc_3_  109 110 111 112
        at irq_acc_4_  109 110 111 112
        at irq_acc_5_  109 110 111 112
        at irq_acc_6_  109 110 111 112
        at irq_acc_7_  109 110 111 112
        at irq_acc_8_  109 110 111 112
        at irq_acc_9_  109 110 111 112
        at dma_addr_10_  111 112 113 114
        at dma_addr_11_  111 112 113 114
        at dma_addr_12_  111 112 113 114
        at dma_addr_13_  111 112 113 114
        at dma_addr_14_  111 112 113 114
        at dma_addr_15_  111 112 113 114
        at dma_addr_1_  111 112 113 114
        at dma_addr_2_  111 112 113 114
        at dma_addr_3_  111 112 113 114
        at dma_addr_4_  111 112 113 114
        at dma_addr_5_  111 112 113 114
        at dma_addr_6_  111 112 113 114
        at dma_addr_7_  111 112 113 114
        at dma_addr_8_  111 112 113 114
        at dma_addr_9_  111 112 113 114
        at dma_din_0_  112 113 114 115
        at dma_din_10_  112 113 114 115
        at dma_din_11_  112 113 114 115
        at dma_din_12_  112 113 114 115
        at dma_din_13_  112 113 114 115
        at dma_din_14_  112 113 114 115
        at dma_din_15_  112 113 114 115
        at dma_din_1_  112 113 114 115
        at dma_din_2_  112 113 114 115
        at dma_din_3_  112 113 114 115
        at dma_din_4_  112 113 114 115
        at dma_din_5_  112 113 114 115
        at dma_din_6_  112 113 114 115
        at dma_din_7_  112 113 114 115
        at dma_din_8_  112 113 114 115
        at dma_din_9_  112 113 114 115
        at dma_en 113 114 115 116
        at dma_priority 114 115 116 117
        at dma_we_0_  115 116 117 118
        at dma_we_1_  115 116 117 118
        at dma_wkup 116 117 118 119
        at nmi 117 118 119 120
        at per_dout_0_  118 119 120 121
        at per_dout_10_  118 119 120 121
        at per_dout_11_  118 119 120 121
        at per_dout_12_  118 119 120 121
        at per_dout_13_  118 119 120 121
        at per_dout_14_  118 119 120 121
        at per_dout_15_  118 119 120 121
        at per_dout_1_  118 119 120 121
        at per_dout_2_  118 119 120 121
        at per_dout_3_  118 119 120 121
        at per_dout_4_  118 119 120 121
        at per_dout_5_  118 119 120 121
        at per_dout_6_  118 119 120 121
        at per_dout_7_  118 119 120 121
        at per_dout_8_  118 119 120 121
        at per_dout_9_  118 119 120 121
        at pmem_dout_0_  119 120 121 122
        at pmem_dout_10_  119 120 121 122
        at pmem_dout_11_  119 120 121 122
        at pmem_dout_12_  119 120 121 122
        at pmem_dout_13_  119 120 121 122
        at pmem_dout_14_  119 120 121 122
        at pmem_dout_15_  119 120 121 122
        at pmem_dout_1_  119 120 121 122
        at pmem_dout_2_  119 120 121 122
        at pmem_dout_3_  119 120 121 122
        at pmem_dout_4_  119 120 121 122
        at pmem_dout_5_  119 120 121 122
        at pmem_dout_6_  119 120 121 122
        at pmem_dout_7_  119 120 121 122
        at pmem_dout_8_  119 120 121 122
        at pmem_dout_9_  119 120 121 122
        at reset_n 120 121 122 123
        at scan_enable 121 122 123 124
        at scan_mode 122 123 124 125
        slew dco_clk dco_clk dco_clk dco_clk dco_clk
        slew lfxt_clk lfxt_clk lfxt_clk lfxt_clk lfxt_clk
        slew cpu_en 150 151 152 153
        slew dbg_en 151 152 153 154
        slew dbg_i2c_addr_0_  152 153 154 155
        slew dbg_i2c_addr_1_  152 153 154 155
        slew dbg_i2c_addr_2_  152 153 154 155
        slew dbg_i2c_addr_3_  152 153 154 155
        slew dbg_i2c_addr_4_  152 153 154 155
        slew dbg_i2c_addr_5_  152 153 154 155
        slew dbg_i2c_addr_6_  152 153 154 155
        slew dbg_i2c_broadcast_0_  153 154 155 156
        slew dbg_i2c_broadcast_1_  153 154 155 156
        slew dbg_i2c_broadcast_2_  153 154 155 156
        slew dbg_i2c_broadcast_3_  153 154 155 156
        slew dbg_i2c_broadcast_4_  153 154 155 156
        slew dbg_i2c_broadcast_5_  153 154 155 156
        slew dbg_i2c_broadcast_6_  153 154 155 156
        slew dbg_i2c_scl 154 155 156 157
        slew dbg_i2c_sda_in 155 156 157 158
        slew dbg_uart_rxd 156 157 158 159
        slew dmem_dout_0_  158 159 160 161
        slew dmem_dout_10_  158 159 160 161
        slew dmem_dout_11_  158 159 160 161
        slew dmem_dout_12_  158 159 160 161
        slew dmem_dout_13_  158 159 160 161
        slew dmem_dout_14_  158 159 160 161
        slew dmem_dout_15_  158 159 160 161
        slew dmem_dout_1_  158 159 160 161
        slew dmem_dout_2_  158 159 160 161
        slew dmem_dout_3_  158 159 160 161
        slew dmem_dout_4_  158 159 160 161
        slew dmem_dout_5_  158 159 160 161
        slew dmem_dout_6_  158 159 160 161
        slew dmem_dout_7_  158 159 160 161
        slew dmem_dout_8_  158 159 160 161
        slew dmem_dout_9_  158 159 160 161
        slew irq_0_  159 160 161 162
        slew irq_10_  159 160 161 162
        slew irq_11_  159 160 161 162
        slew irq_12_  159 160 161 162
        slew irq_13_  159 160 161 162
        slew irq_1_  159 160 161 162
        slew irq_2_  159 160 161 162
        slew irq_3_  159 160 161 162
        slew irq_4_  159 160 161 162
        slew irq_5_  159 160 161 162
        slew irq_6_  159 160 161 162
        slew irq_7_  159 160 161 162
        slew irq_8_  159 160 161 162
        slew irq_9_  159 160 161 162
        slew irq_acc_0_  159 160 161 162
        slew irq_acc_10_  159 160 161 162
        slew irq_acc_11_  159 160 161 162
        slew irq_acc_12_  159 160 161 162
        slew irq_acc_13_  159 160 161 162
        slew irq_acc_1_  159 160 161 162
        slew irq_acc_2_  159 160 161 162
        slew irq_acc_3_  159 160 161 162
        slew irq_acc_4_  159 160 161 162
        slew irq_acc_5_  159 160 161 162
        slew irq_acc_6_  159 160 161 162
        slew irq_acc_7_  159 160 161 162
        slew irq_acc_8_  159 160 161 162
        slew irq_acc_9_  159 160 161 162
        slew dma_addr_10_  161 162 163 164
        slew dma_addr_11_  161 162 163 164
        slew dma_addr_12_  161 162 163 164
        slew dma_addr_13_  161 162 163 164
        slew dma_addr_14_  161 162 163 164
        slew dma_addr_15_  161 162 163 164
        slew dma_addr_1_  161 162 163 164
        slew dma_addr_2_  161 162 163 164
        slew dma_addr_3_  161 162 163 164
        slew dma_addr_4_  161 162 163 164
        slew dma_addr_5_  161 162 163 164
        slew dma_addr_6_  161 162 163 164
        slew dma_addr_7_  161 162 163 164
        slew dma_addr_8_  161 162 163 164
        slew dma_addr_9_  161 162 163 164
        slew dma_din_0_  162 163 164 165
        slew dma_din_10_  162 163 164 165
        slew dma_din_11_  162 163 164 165
        slew dma_din_12_  162 163 164 165
        slew dma_din_13_  162 163 164 165
        slew dma_din_14_  162 163 164 165
        slew dma_din_15_  162 163 164 165
        slew dma_din_1_  162 163 164 165
        slew dma_din_2_  162 163 164 165
        slew dma_din_3_  162 163 164 165
        slew dma_din_4_  162 163 164 165
        slew dma_din_5_  162 163 164 165
        slew dma_din_6_  162 163 164 165
        slew dma_din_7_  162 163 164 165
        slew dma_din_8_  162 163 164 165
        slew dma_din_9_  162 163 164 165
        slew dma_en 163 164 165 166
        slew dma_priority 164 165 166 167
        slew dma_we_0_  165 166 167 168
        slew dma_we_1_  165 166 167 168
        slew dma_wkup 166 167 168 169
        slew nmi 167 168 169 170
        slew per_dout_0_  168 169 170 171
        slew per_dout_10_  168 169 170 171
        slew per_dout_11_  168 169 170 171
        slew per_dout_12_  168 169 170 171
        slew per_dout_13_  168 169 170 171
        slew per_dout_14_  168 169 170 171
        slew per_dout_15_  168 169 170 171
        slew per_dout_1_  168 169 170 171
        slew per_dout_2_  168 169 170 171
        slew per_dout_3_  168 169 170 171
        slew per_dout_4_  168 169 170 171
        slew per_dout_5_  168 169 170 171
        slew per_dout_6_  168 169 170 171
        slew per_dout_7_  168 169 170 171
        slew per_dout_8_  168 169 170 171
        slew per_dout_9_  168 169 170 171
        slew pmem_dout_0_  169 170 171 172
        slew pmem_dout_10_  169 170 171 172
        slew pmem_dout_11_  169 170 171 172
        slew pmem_dout_12_  169 170 171 172
        slew pmem_dout_13_  169 170 171 172
        slew pmem_dout_14_  169 170 171 172
        slew pmem_dout_15_  169 170 171 172
        slew pmem_dout_1_  169 170 171 172
        slew pmem_dout_2_  169 170 171 172
        slew pmem_dout_3_  169 170 171 172
        slew pmem_dout_4_  169 170 171 172
        slew pmem_dout_5_  169 170 171 172
        slew pmem_dout_6_  169 170 171 172
        slew pmem_dout_7_  169 170 171 172
        slew pmem_dout_8_  169 170 171 172
        slew pmem_dout_9_  169 170 171 172
        slew reset_n 170 171 172 173
        slew scan_enable 171 172 173 174
        slew scan_mode 172 173 174 175
        rat aclk 100 101 102 103
        rat aclk_en 101 102 103 104
        rat dbg_freeze 102 103 104 105
        rat dbg_i2c_sda_out 103 104 105 106
        rat dbg_uart_txd 104 105 106 107
        rat dco_enable 105 106 107 108
        rat dco_wkup 106 107 108 109
        rat dmem_addr 107 108 109 110
        rat dmem_cen 108 109 110 111
        rat dmem_din 109 110 111 112
        rat dmem_wen 110 111 112 113
        rat irq_acc 111 112 113 114
        rat lfxt_enable 112 113 114 115
        rat lfxt_wkup 113 114 115 116
        rat mclk 114 115 116 117
        rat dma_dout 115 116 117 118
        rat dma_ready 116 117 118 119
        rat dma_resp 117 118 119 120
        rat per_addr_0_  118 119 120 121
        rat per_addr_10_  118 119 120 121
        rat per_addr_11_  118 119 120 121
        rat per_addr_12_  118 119 120 121
        rat per_addr_13_  118 119 120 121
        rat per_addr_1_  118 119 120 121
        rat per_addr_2_  118 119 120 121
        rat per_addr_3_  118 119 120 121
        rat per_addr_4_  118 119 120 121
        rat per_addr_5_  118 119 120 121
        rat per_addr_6_  118 119 120 121
        rat per_addr_7_  118 119 120 121
        rat per_addr_8_  118 119 120 121
        rat per_addr_9_  118 119 120 121
        rat per_din_0_  119 120 121 122
        rat per_din_10_  119 120 121 122
        rat per_din_11_  119 120 121 122
        rat per_din_12_  119 120 121 122
        rat per_din_13_  119 120 121 122
        rat per_din_14_  119 120 121 122
        rat per_din_15_  119 120 121 122
        rat per_din_1_  119 120 121 122
        rat per_din_2_  119 120 121 122
        rat per_din_3_  119 120 121 122
        rat per_din_4_  119 120 121 122
        rat per_din_5_  119 120 121 122
        rat per_din_6_  119 120 121 122
        rat per_din_7_  119 120 121 122
        rat per_din_8_  119 120 121 122
        rat per_din_9_  119 120 121 122
        rat per_en 120 121 122 123
        rat per_we_0_  121 122 123 124
        rat per_we_1_  121 122 123 124
        rat pmem_addr 122 123 124 125
        rat pmem_cen 123 124 125 126
        rat pmem_din 124 125 126 127
        rat pmem_wen 125 126 127 128
        rat puc_rst 126 127 128 129
        rat smclk 127 128 129 130
        rat smclk_en 128 129 130 131
        load aclk 10
        load aclk_en 11
        load dbg_freeze 12
        load dbg_i2c_sda_out 13
        load dbg_uart_txd 14
        load dco_enable 15
        load dco_wkup 16
        load dmem_addr 17
        load dmem_cen 18
        load dmem_din 19
        load dmem_wen 20
        load irq_acc 21
        load lfxt_enable 22
        load lfxt_wkup 23
        load mclk 24
        load dma_dout 25
        load dma_ready 26
        load dma_resp 27
        load per_addr_0_  28
        load per_addr_10_  28
        load per_addr_11_  28
        load per_addr_12_  28
        load per_addr_13_  28
        load per_addr_1_  28
        load per_addr_2_  28
        load per_addr_3_  28
        load per_addr_4_  28
        load per_addr_5_  28
        load per_addr_6_  28
        load per_addr_7_  28
        load per_addr_8_  28
        load per_addr_9_  28
        load per_din_0_  29
        load per_din_10_  29
        load per_din_11_  29
        load per_din_12_  29
        load per_din_13_  29
        load per_din_14_  29
        load per_din_15_  29
        load per_din_1_  29
        load per_din_2_  29
        load per_din_3_  29
        load per_din_4_  29
        load per_din_5_  29
        load per_din_6_  29
        load per_din_7_  29
        load per_din_8_  29
        load per_din_9_  29
        load per_en 30
        load per_we_0_  31
        load per_we_1_  31
        load pmem_addr 32
        load pmem_cen 33
        load pmem_din 34
        load pmem_wen 35
        load puc_rst 36
        load smclk 37
        load smclk_en 38

     ```




  
  












