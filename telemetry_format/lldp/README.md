# LLDP

LLDP telemetry结构如下（JSON格式）.

<pre>
{
    "protocols": {
        "lldp": {
            "enable": "true",
            "advertisement-interval": "30",
            "interface" : [
                {
                    "te-1/1/2": {
                        "status": "tx-rx",
                        "statistics" : {
                            "tx" : {
                                "frames_out_total" : "3"
                            },
                            "rx" : {
                                "frames_discarded_total" : "0",
                                "frames_in_erros_total" : "0",
                                "frames_in_total" : "0",
                                "tlvs_discarded_total" : "0",
                                "tlvs_unrecognized_total" : "0",
                                "ageouts_total" : "0"
                            }
                        },
                        "local_info" : {
                            "port_id_subtype" : "",
                            "port_id" : "",
                            "port_desc" : ""
                        },
                        "neighbor" : {
                            "interface_name" : "te-1/1/11",
                            "chassis_type" : "",
                            "chassis_id" : "",
                            "port_type" : "",
                            "port_id" : "",
                            "port_description" : "",
                            "system_name" : "",
                            "system_description" : "",
                            "capabilities_supported" : "",
                            "capabilities_enabled" : "",
                            "management_address" : [
                                {
                                    "man_address_type" : "",
                                    "man_address" : "" ,
                                    "man_interface_type" : "",
                                    "man_interface_id" : "",
                                    "man_address_oid" : ""
                                }
                            ] 
                        },
                        "unknown_tlvs_info" : [
                            "rem_unknown_tlv_type" : "",
                            "rem_unknown_tlv_info" : ""
                        ],
                        "organization_tlvs_info" : [
                            {
                                "rem_organization_oui" : "",
                                "rem_organization_subtype" : "",
                                "rem_organization_info" : ""
                            }
                        ]
                    }
                }
            ],
            "reinit-delay": "2",
            "transmit-delay": "2",
            "hold-time-multiplier": "4",
            "tlv-select": {
                "mac-phy-cfg": {
                    "enable": "true"
                },
                "management-address": {
                    "enable": "true"
                },
                "port-description": {
                    "enable": "true"
                },
                "port-vlan": {
                    "enable": "true"
                },
                "system-capabilities": {
                    "enable": "true"
                },
                "system-description": {
                    "enable": "true"
                },
                "system-name": {
                    "enable": "true"
                }
            }
        }
    }
}
</pre>
