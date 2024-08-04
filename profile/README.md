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
3. Clone the needed NXP repositories to *hardware/nxp*.
    > ###### About nxp
    > Since Xiaomi SM8650 series devices are using **[StrongBox](https://source.android.com/docs/security/best-practices/hardware#strongbox-keymaster)**<br>
    > as an implementation of the Keymaster or Keymint HAL,<br>
    > and at the same time, the nxp part of LineageOS source code is outdated.<br>
    > We just use the [nxp upstream](https://github.com/orgs/NXPNFCProject) source code instead for now.
    
    | Source                                                                                        | Path                                  |
    | --------------------------------------------------------------------------------------------- | ------------------------------------- |
    | [nfcandroid_keymint_hidlimpl](https://github.com/NXPNFCProject/nfcandroid_keymint_hidlimpl)   | hardware/nxp/keymint                  |
    | [nfcandroid_nfc_hidlimpl](https://github.com/NXPNFCProject/nfcandroid_nfc_hidlimpl)           | hardware/nxp/nfc                      |
    | [nfcandroid_nxp_ese_clients](https://github.com/NXPNFCProject/nfcandroid_nxp_ese_clients)     | hardware/nxp/secure_element_extns     |
    | [nfcandroid_se_hidlimpl](https://github.com/NXPNFCProject/nfcandroid_se_hidlimpl)             | hardware/nxp/secure_element           |
    | [nfcandroid_weaver_hidlimpl](https://github.com/NXPNFCProject/nfcandroid_weaver_hidlimpl)     | hardware/nxp/weaver                   |

    **Attention: We are using branch *br_android_ncihalx_comm_15* in all of the above repositories**
4. Build
    > If you want to accelerate the compile, you can configure ccache before compiling.
    ``` At the top of source code
    . build/envsetup.sh
    lunch <product>-<release>-<variant>
    # Such as: lunch lineage_houji-ap2a-userdebug
    mka bacon
    ```
    If there is no error report, you can find your newly build in<br>
    _out/target/product/DEVICE/_
