# **FORCE PUSH WARNING**

# Org for Xiaomi SM8650 
#### SOC
|      Basic | Spec Sheet                                                                  					                       |
| ---------: | :------------------------------------------------------------------------------------------------------------------ |
|        SoC | Qualcomm Snapdragon 8 Gen 3 (SM8650-AB)                                              				        	   |
|        CPU | 1x Cortex-X4 (3.3 Ghz) <br> 3x Cortex-A720 (3.15 GHz) <br> 2x Cortex-A720 (2.96 Ghz) <br> 2x Cortex-A520 (2.27 GHz) |
|        GPU | Adreno 750 (770 MHz)                                                        					                       |
|	      										    					                                                           |
|	     SoC | Qualcomm Snapdragon 8s Gen 3 (SM8635)					    				                                	   |
| 	     CPU | 1x Cortex-X4 (3.0 GHz) <br> 4x Cortex-A720 (2.8 Ghz) <br> 3x Cortex-A520 (2.0 Ghz)	    		            	   |
|        GPU | Qualcomm Adreno 735	(1.1 GHz)						    				                                           |

#### Devices 
> SM8650 devices

| Device 		        | Codename	    |
| --------------------- | ------------- |
| Xiaomi 14		        | houji 	    |
| Xiaomi 14 Pro 	    | shennong 	    |
| Xiaomi 14 Ultra     	| aurora 	    |
| Redmi K70 Pro 	    | manet 	    |
| Xiaomi Mix Fold 4	| goku			|
| Xiaomi Mix Flip	| ruyi			|

> SM8635 devices 

| Device 		        | Codename      |
| --------------------- | ------------- |
| Xiaomi Civi 4/Pro 	| chenfeng 	    |
| Redmi Turbo 3/Poco F6 | peridot 	    |

#### Build
> _Attention:_<br>
> _Since the Device Trees of sm8650 devices are still WIP,_<br>
> _don't build with our devcie trees until we finish them._

1. Sync the [LineageOS](https://github.com/LineageOS) source code (Branch lineage-21.0).

    See [here](https://github.com/LineageOS/android)
2. Clone the needed repositories of this org to the correct path.
    > LineageOS hasn't tracked sm8650-caf codes of [CodeLinaro](https://git.codelinaro.org/),<br>
    > so we have to do it by ourselves.<br>
    > If LOS already tracked them, just skip this step.
3. Build
    > If you want to accelerate the compile, you can configure ccache before compiling.
    ``` At the top of source code
    . build/envsetup.sh
    lunch <product>-<release>-<variant>
    # Such as: lunch lineage_houji-ap2a-userdebug
    mka bacon
    ```
    If there is no error report, you can find your newly build in<br>
    _out/target/product/DEVICE/_
