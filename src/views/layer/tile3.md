import React, { Component } from 'react';
import ReactDOM from 'react-dom';
import {
  Map,
  TileLayer,
  Base,
} from 'rc-bmap';
import { Input, Button } from 'antd';

const { Point } = Base;

class Example extends Component {
  getTilesUrl = (tileCoord, zoom) => {
    const { x, y } = tileCoord;
    // 根据当前坐标，选取合适的瓦片图
    return "http://lbsyun.baidu.com/jsdemo/img/border.png";
  }

  render() {
    return (
      <div style={{ height: '100vh' }}>
        <Map
          ak="WAeVpuoSBH4NswS30GNbCRrlsmdGB5Gv"
          scrollWheelZoom
          zoom={15}
        >
          <Point name="center" lng="116.404" lat="39.915" />
          <TileLayer 
            getTilesUrl={this.getTilesUrl}
            transparentPng
          />
        </Map>
      </div>
    );
  }
}

ReactDOM.render(
  <Example />,
  document.getElementById('root'),
);
