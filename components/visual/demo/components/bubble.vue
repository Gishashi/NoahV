<template>
    <NvMDBubble :axis="areaObj"
                :axis-status="abnAreaObj"
                :show-legend="true"
                :showTooltips="true"
                :tooltip="tooltip"
                :legendStatus="legendStatus"
                groups-icon="search"
                @toDetail="toDetail"
    ></NvMDBubble>
</template>

<script>
const areaObj = {
    '华南': [
        'GZA',
        'GZB',
        'GZC',
        'GZD',
        'GZE',
        'GZF'
    ],
    '华北': [
        'HBA',
        'HBB',
        'HBC',
        'HBD',
        'HBE',
        'HBF',
        'HBG',
        'HBH',
        'HBI',
        'HBJ',
        'HBK',
        'HBL',
        'HBM',
        'HBN',
        'HBO',
        'HBP',
        'HBQ',
        'HBR'
    ],
    '华东': [
        'HDA',
        'HDB',
        'HDC',
        'HDD',
        'HDE',
        'HDF',
        'HDG',
        'HDH',
        'HDI',
        'HDJ',
        'HDK',
        'HDL'
    ],
    'C区': [
        'BDC1',
        'BDC2'
    ]
};
const abnAreaObj = {
    'GZB': {
        'status': {
            'HBN': 'warning',
            'GZC': 'special'
        }
    },
    'HBF': {
        'status': {
            'GZF': 'warning'
        }
    },
    'HBD': {
        'status': {
            'GZF': 'error'
        }
    },
    'HBE': {
        'status': {
            'HBL': 'error',
            'GZA': 'error',
            'HBO': 'error',
            'GZC': 'error',
            'HBR': 'error',
            'HDJ': 'error',
            'HBJ': 'error'
        }
    },
    'HBH': {
        'status': {
            'HBH': 'error'
        },
        'drillDownLists': ['HBHa', 'HBHb']
    },
    'GZF': {
        'status': {
            'HBL': 'error'
        }
    },
    'HDH': {
        'status': {
            'HBA': 'error'
        }
    },
    'HBA': {
        'status': {
            'HBE': 'error',
            'HDK': 'error'
        }
    },
    'HDG': {
        'status': {
            'HDC': 'warning',
            'HBN': 'warning',
            'HBD': 'normal',
            'GZC': 'warning'
        }
    },
    'HBQ': {
        'status': {
            'GZF': 'warning'
        }
    },
    'HDK': {
        'status': {
            'HDA': 'warning',
            'HDF': 'warning'
        }
    },
    'HBC': {
        'status': {
            'HBA': 'normal',
            'HBF': 'warning'
        }
    },
    'GZD': {
        'status': {
            'HBE': 'error'
        }
    },
    'HBO': {
        'status': {
            'HBP': 'error'
        }
    },
    'HBL': {
        'status': {
            'HBL': 'normal'
        }
    },
    'BDC1': {
        'status': {
            'HBL': 'error',
            'BDC1': 'normal'
        }
    },
    'BDC2': {
        'status': {
            'YQ02': 'normal',
            'BDC1': 'error'
        }
    }
};
const axisFilterLists = ['GZA', 'GZB'];
const legendStatus = [
    {
        name: '正常延迟区域',
        color: '#3a62ca',
        icon: 'search',
        type: 'normal',
        typeName: '正常延迟工作区',
        typeSymbol: 'triangle', // 'circle', 'rect', 'roundRect', 'triangle', 'diamond', 'pin', 'arrow', 'none', image://url (database64) path://
        typeSymbolSize: 10
    },
    {
        name: '轻微延迟区域',
        color: '#ef8700',
        type: 'warning'
    },
    {
        name: '严重延迟区域',
        color: '#f62626',
        type: 'error'
    },
    {
        name: '无响应',
        color: 'black',
        type: 'special'
    }
];

export default {
    name: 'buHBAle',
    data() {
        return {
            areaObj,
            abnAreaObj,
            axisFilterLists,
            legendStatus
        };
    },
    computed: {
        tooltip() {
            return function (item) {
                return item.seriesName;
            };
        }
    },
    methods: {
        toDetail(info) {
            console.log(info)
        }
    }
};
</script>

<style lang="less">

</style>
