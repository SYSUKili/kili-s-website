---
title: non-parametric
author: kili
date: '2024-01-01'
slug: non-parametric
categories:
  - R
tags:
  - R
  - non-peremetric
---

<script src="{{< blogdown/postref >}}index_files/kePrint/kePrint.js"></script>
<link href="{{< blogdown/postref >}}index_files/lightable/lightable.css" rel="stylesheet" />
<script src="{{< blogdown/postref >}}index_files/kePrint/kePrint.js"></script>
<link href="{{< blogdown/postref >}}index_files/lightable/lightable.css" rel="stylesheet" />
<script src="{{< blogdown/postref >}}index_files/kePrint/kePrint.js"></script>

<link href="{{< blogdown/postref >}}index_files/lightable/lightable.css" rel="stylesheet" />

> *吾生也有涯，而知也无涯，以有涯随无涯，殆已。*

# 数据描述与背景导入

## 各变量介绍

<table class="table table-bordered" style="margin-left: auto; margin-right: auto;">
<caption>
<span id="tab:unnamed-chunk-2"></span>Table 1: CTG数据
</caption>
<thead>
<tr>
<th style="text-align:left;color: black !important;background-color: #98F5FF !important;">
变量名
</th>
<th style="text-align:left;color: black !important;background-color: #98F5FF !important;">
数据类型
</th>
<th style="text-align:left;color: black !important;background-color: #98F5FF !important;">
含义
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
fixed acidity
</td>
<td style="text-align:left;">
连续型变量
</td>
<td style="text-align:left;">
固定酸度
</td>
</tr>
<tr>
<td style="text-align:left;">
volatile acidity
</td>
<td style="text-align:left;">
连续型变量
</td>
<td style="text-align:left;">
挥发性酸度
</td>
</tr>
<tr>
<td style="text-align:left;">
citric acid
</td>
<td style="text-align:left;">
连续型变量
</td>
<td style="text-align:left;">
柠檬酸
</td>
</tr>
<tr>
<td style="text-align:left;">
residual sugar
</td>
<td style="text-align:left;">
连续型变量
</td>
<td style="text-align:left;">
残糖
</td>
</tr>
<tr>
<td style="text-align:left;">
chlorides
</td>
<td style="text-align:left;">
连续型变量
</td>
<td style="text-align:left;">
氯化物
</td>
</tr>
<tr>
<td style="text-align:left;">
free sulfur dioxide
</td>
<td style="text-align:left;">
连续型变量
</td>
<td style="text-align:left;">
游离二氧化硫
</td>
</tr>
<tr>
<td style="text-align:left;">
total sulfur dioxide
</td>
<td style="text-align:left;">
连续型变量
</td>
<td style="text-align:left;">
总二氧化硫
</td>
</tr>
<tr>
<td style="text-align:left;">
density
</td>
<td style="text-align:left;">
连续型变量
</td>
<td style="text-align:left;">
密度
</td>
</tr>
<tr>
<td style="text-align:left;">
pH
</td>
<td style="text-align:left;">
连续型变量
</td>
<td style="text-align:left;">
pH值
</td>
</tr>
<tr>
<td style="text-align:left;">
sulphates
</td>
<td style="text-align:left;">
连续型变量
</td>
<td style="text-align:left;">
硫酸盐
</td>
</tr>
<tr>
<td style="text-align:left;">
alcohol
</td>
<td style="text-align:left;">
连续型变量
</td>
<td style="text-align:left;">
酒精浓度
</td>
</tr>
<tr>
<td style="text-align:left;">
quality
</td>
<td style="text-align:left;">
有序分类变量
</td>
<td style="text-align:left;">
酒质量3-8
</td>
</tr>
</tbody>
</table>

## 数据预览

<div id="tgffnfjemi" style="padding-left:0px;padding-right:0px;padding-top:10px;padding-bottom:10px;overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>#tgffnfjemi table {
  font-family: system-ui, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
&#10;#tgffnfjemi thead, #tgffnfjemi tbody, #tgffnfjemi tfoot, #tgffnfjemi tr, #tgffnfjemi td, #tgffnfjemi th {
  border-style: none;
}
&#10;#tgffnfjemi p {
  margin: 0;
  padding: 0;
}
&#10;#tgffnfjemi .gt_table {
  display: table;
  border-collapse: collapse;
  line-height: normal;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  font-weight: normal;
  font-style: normal;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 0px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 0px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}
&#10;#tgffnfjemi .gt_caption {
  padding-top: 4px;
  padding-bottom: 4px;
}
&#10;#tgffnfjemi .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}
&#10;#tgffnfjemi .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 3px;
  padding-bottom: 5px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}
&#10;#tgffnfjemi .gt_heading {
  background-color: #FFFFFF;
  text-align: left;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}
&#10;#tgffnfjemi .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#tgffnfjemi .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}
&#10;#tgffnfjemi .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}
&#10;#tgffnfjemi .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}
&#10;#tgffnfjemi .gt_column_spanner_outer:first-child {
  padding-left: 0;
}
&#10;#tgffnfjemi .gt_column_spanner_outer:last-child {
  padding-right: 0;
}
&#10;#tgffnfjemi .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 5px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}
&#10;#tgffnfjemi .gt_spanner_row {
  border-bottom-style: hidden;
}
&#10;#tgffnfjemi .gt_group_heading {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  text-align: left;
}
&#10;#tgffnfjemi .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}
&#10;#tgffnfjemi .gt_from_md > :first-child {
  margin-top: 0;
}
&#10;#tgffnfjemi .gt_from_md > :last-child {
  margin-bottom: 0;
}
&#10;#tgffnfjemi .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}
&#10;#tgffnfjemi .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#tgffnfjemi .gt_stub_row_group {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
  vertical-align: top;
}
&#10;#tgffnfjemi .gt_row_group_first td {
  border-top-width: 2px;
}
&#10;#tgffnfjemi .gt_row_group_first th {
  border-top-width: 2px;
}
&#10;#tgffnfjemi .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#tgffnfjemi .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}
&#10;#tgffnfjemi .gt_first_summary_row.thick {
  border-top-width: 2px;
}
&#10;#tgffnfjemi .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#tgffnfjemi .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#tgffnfjemi .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}
&#10;#tgffnfjemi .gt_last_grand_summary_row_top {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: double;
  border-bottom-width: 6px;
  border-bottom-color: #D3D3D3;
}
&#10;#tgffnfjemi .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}
&#10;#tgffnfjemi .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#tgffnfjemi .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}
&#10;#tgffnfjemi .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#tgffnfjemi .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}
&#10;#tgffnfjemi .gt_sourcenote {
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#tgffnfjemi .gt_left {
  text-align: left;
}
&#10;#tgffnfjemi .gt_center {
  text-align: center;
}
&#10;#tgffnfjemi .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}
&#10;#tgffnfjemi .gt_font_normal {
  font-weight: normal;
}
&#10;#tgffnfjemi .gt_font_bold {
  font-weight: bold;
}
&#10;#tgffnfjemi .gt_font_italic {
  font-style: italic;
}
&#10;#tgffnfjemi .gt_super {
  font-size: 65%;
}
&#10;#tgffnfjemi .gt_footnote_marks {
  font-size: 75%;
  vertical-align: 0.4em;
  position: initial;
}
&#10;#tgffnfjemi .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}
&#10;#tgffnfjemi .gt_indent_1 {
  text-indent: 5px;
}
&#10;#tgffnfjemi .gt_indent_2 {
  text-indent: 10px;
}
&#10;#tgffnfjemi .gt_indent_3 {
  text-indent: 15px;
}
&#10;#tgffnfjemi .gt_indent_4 {
  text-indent: 20px;
}
&#10;#tgffnfjemi .gt_indent_5 {
  text-indent: 25px;
}
</style>
<table class="gt_table" data-quarto-disable-processing="false" data-quarto-bootstrap="false">
  <thead>
    <tr class="gt_heading">
      <td colspan="15" class="gt_heading gt_title gt_font_normal gt_bottom_border" style>Correlation Table</td>
    </tr>
    &#10;    <tr class="gt_col_headings">
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" scope="col" id="Variable">Variable</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="Mean">Mean</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="SD">SD</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="1">1</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="2">2</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="3">3</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="4">4</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="5">5</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="6">6</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="7">7</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="8">8</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="9">9</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="10">10</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="11">11</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="12">12</th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr><td headers="Variable" class="gt_row gt_left">1. Fixed.acidity</td>
<td headers="Mean" class="gt_row gt_right">8.32</td>
<td headers="SD" class="gt_row gt_right">1.74</td>
<td headers="1" class="gt_row gt_right">--</td>
<td headers="2" class="gt_row gt_right"></td>
<td headers="3" class="gt_row gt_right"></td>
<td headers="4" class="gt_row gt_right"></td>
<td headers="5" class="gt_row gt_right"></td>
<td headers="6" class="gt_row gt_right"></td>
<td headers="7" class="gt_row gt_right"></td>
<td headers="8" class="gt_row gt_right"></td>
<td headers="9" class="gt_row gt_right"></td>
<td headers="10" class="gt_row gt_right"></td>
<td headers="11" class="gt_row gt_right"></td>
<td headers="12" class="gt_row gt_right"></td></tr>
    <tr><td headers="Variable" class="gt_row gt_left">2. Volatile.acidity</td>
<td headers="Mean" class="gt_row gt_right">0.53</td>
<td headers="SD" class="gt_row gt_right">0.18</td>
<td headers="1" class="gt_row gt_right">-.26**  </td>
<td headers="2" class="gt_row gt_right">--</td>
<td headers="3" class="gt_row gt_right"></td>
<td headers="4" class="gt_row gt_right"></td>
<td headers="5" class="gt_row gt_right"></td>
<td headers="6" class="gt_row gt_right"></td>
<td headers="7" class="gt_row gt_right"></td>
<td headers="8" class="gt_row gt_right"></td>
<td headers="9" class="gt_row gt_right"></td>
<td headers="10" class="gt_row gt_right"></td>
<td headers="11" class="gt_row gt_right"></td>
<td headers="12" class="gt_row gt_right"></td></tr>
    <tr><td headers="Variable" class="gt_row gt_left">3. Citric.acid</td>
<td headers="Mean" class="gt_row gt_right">0.27</td>
<td headers="SD" class="gt_row gt_right">0.19</td>
<td headers="1" class="gt_row gt_right">.67**  </td>
<td headers="2" class="gt_row gt_right">-.55**  </td>
<td headers="3" class="gt_row gt_right">--</td>
<td headers="4" class="gt_row gt_right"></td>
<td headers="5" class="gt_row gt_right"></td>
<td headers="6" class="gt_row gt_right"></td>
<td headers="7" class="gt_row gt_right"></td>
<td headers="8" class="gt_row gt_right"></td>
<td headers="9" class="gt_row gt_right"></td>
<td headers="10" class="gt_row gt_right"></td>
<td headers="11" class="gt_row gt_right"></td>
<td headers="12" class="gt_row gt_right"></td></tr>
    <tr><td headers="Variable" class="gt_row gt_left">4. Residual.sugar</td>
<td headers="Mean" class="gt_row gt_right">2.54</td>
<td headers="SD" class="gt_row gt_right">1.41</td>
<td headers="1" class="gt_row gt_right">.11**  </td>
<td headers="2" class="gt_row gt_right">.00    </td>
<td headers="3" class="gt_row gt_right">.14**  </td>
<td headers="4" class="gt_row gt_right">--</td>
<td headers="5" class="gt_row gt_right"></td>
<td headers="6" class="gt_row gt_right"></td>
<td headers="7" class="gt_row gt_right"></td>
<td headers="8" class="gt_row gt_right"></td>
<td headers="9" class="gt_row gt_right"></td>
<td headers="10" class="gt_row gt_right"></td>
<td headers="11" class="gt_row gt_right"></td>
<td headers="12" class="gt_row gt_right"></td></tr>
    <tr><td headers="Variable" class="gt_row gt_left">5. Chlorides</td>
<td headers="Mean" class="gt_row gt_right">0.09</td>
<td headers="SD" class="gt_row gt_right">0.05</td>
<td headers="1" class="gt_row gt_right">.09**  </td>
<td headers="2" class="gt_row gt_right">.06*   </td>
<td headers="3" class="gt_row gt_right">.20**  </td>
<td headers="4" class="gt_row gt_right">.06*   </td>
<td headers="5" class="gt_row gt_right">--</td>
<td headers="6" class="gt_row gt_right"></td>
<td headers="7" class="gt_row gt_right"></td>
<td headers="8" class="gt_row gt_right"></td>
<td headers="9" class="gt_row gt_right"></td>
<td headers="10" class="gt_row gt_right"></td>
<td headers="11" class="gt_row gt_right"></td>
<td headers="12" class="gt_row gt_right"></td></tr>
    <tr><td headers="Variable" class="gt_row gt_left">6. Free.sulfur.dioxide</td>
<td headers="Mean" class="gt_row gt_right">15.87</td>
<td headers="SD" class="gt_row gt_right">10.46</td>
<td headers="1" class="gt_row gt_right">-.15**  </td>
<td headers="2" class="gt_row gt_right">-.01    </td>
<td headers="3" class="gt_row gt_right">-.06*   </td>
<td headers="4" class="gt_row gt_right">.19**  </td>
<td headers="5" class="gt_row gt_right">.01    </td>
<td headers="6" class="gt_row gt_right">--</td>
<td headers="7" class="gt_row gt_right"></td>
<td headers="8" class="gt_row gt_right"></td>
<td headers="9" class="gt_row gt_right"></td>
<td headers="10" class="gt_row gt_right"></td>
<td headers="11" class="gt_row gt_right"></td>
<td headers="12" class="gt_row gt_right"></td></tr>
    <tr><td headers="Variable" class="gt_row gt_left">7. Total.sulfur.dioxide</td>
<td headers="Mean" class="gt_row gt_right">46.47</td>
<td headers="SD" class="gt_row gt_right">32.90</td>
<td headers="1" class="gt_row gt_right">-.11**  </td>
<td headers="2" class="gt_row gt_right">.08**  </td>
<td headers="3" class="gt_row gt_right">.04    </td>
<td headers="4" class="gt_row gt_right">.20**  </td>
<td headers="5" class="gt_row gt_right">.05    </td>
<td headers="6" class="gt_row gt_right">.67**  </td>
<td headers="7" class="gt_row gt_right">--</td>
<td headers="8" class="gt_row gt_right"></td>
<td headers="9" class="gt_row gt_right"></td>
<td headers="10" class="gt_row gt_right"></td>
<td headers="11" class="gt_row gt_right"></td>
<td headers="12" class="gt_row gt_right"></td></tr>
    <tr><td headers="Variable" class="gt_row gt_left">8. Density</td>
<td headers="Mean" class="gt_row gt_right">1.00</td>
<td headers="SD" class="gt_row gt_right">0.00</td>
<td headers="1" class="gt_row gt_right">.67**  </td>
<td headers="2" class="gt_row gt_right">.02    </td>
<td headers="3" class="gt_row gt_right">.36**  </td>
<td headers="4" class="gt_row gt_right">.36**  </td>
<td headers="5" class="gt_row gt_right">.20**  </td>
<td headers="6" class="gt_row gt_right">-.02    </td>
<td headers="7" class="gt_row gt_right">.07**  </td>
<td headers="8" class="gt_row gt_right">--</td>
<td headers="9" class="gt_row gt_right"></td>
<td headers="10" class="gt_row gt_right"></td>
<td headers="11" class="gt_row gt_right"></td>
<td headers="12" class="gt_row gt_right"></td></tr>
    <tr><td headers="Variable" class="gt_row gt_left">9. PH</td>
<td headers="Mean" class="gt_row gt_right">3.31</td>
<td headers="SD" class="gt_row gt_right">0.15</td>
<td headers="1" class="gt_row gt_right">-.68**  </td>
<td headers="2" class="gt_row gt_right">.23**  </td>
<td headers="3" class="gt_row gt_right">-.54**  </td>
<td headers="4" class="gt_row gt_right">-.09**  </td>
<td headers="5" class="gt_row gt_right">-.27**  </td>
<td headers="6" class="gt_row gt_right">.07**  </td>
<td headers="7" class="gt_row gt_right">-.07**  </td>
<td headers="8" class="gt_row gt_right">-.34**  </td>
<td headers="9" class="gt_row gt_right">--</td>
<td headers="10" class="gt_row gt_right"></td>
<td headers="11" class="gt_row gt_right"></td>
<td headers="12" class="gt_row gt_right"></td></tr>
    <tr><td headers="Variable" class="gt_row gt_left">10. Sulphates</td>
<td headers="Mean" class="gt_row gt_right">0.66</td>
<td headers="SD" class="gt_row gt_right">0.17</td>
<td headers="1" class="gt_row gt_right">.18**  </td>
<td headers="2" class="gt_row gt_right">-.26**  </td>
<td headers="3" class="gt_row gt_right">.31**  </td>
<td headers="4" class="gt_row gt_right">.01    </td>
<td headers="5" class="gt_row gt_right">.37**  </td>
<td headers="6" class="gt_row gt_right">.05*   </td>
<td headers="7" class="gt_row gt_right">.04    </td>
<td headers="8" class="gt_row gt_right">.15**  </td>
<td headers="9" class="gt_row gt_right">-.20**  </td>
<td headers="10" class="gt_row gt_right">--</td>
<td headers="11" class="gt_row gt_right"></td>
<td headers="12" class="gt_row gt_right"></td></tr>
    <tr><td headers="Variable" class="gt_row gt_left">11. Alcohol</td>
<td headers="Mean" class="gt_row gt_right">10.42</td>
<td headers="SD" class="gt_row gt_right">1.07</td>
<td headers="1" class="gt_row gt_right">-.06*   </td>
<td headers="2" class="gt_row gt_right">-.20**  </td>
<td headers="3" class="gt_row gt_right">.11**  </td>
<td headers="4" class="gt_row gt_right">.04    </td>
<td headers="5" class="gt_row gt_right">-.22**  </td>
<td headers="6" class="gt_row gt_right">-.07**  </td>
<td headers="7" class="gt_row gt_right">-.21**  </td>
<td headers="8" class="gt_row gt_right">-.50**  </td>
<td headers="9" class="gt_row gt_right">.21**  </td>
<td headers="10" class="gt_row gt_right">.09**  </td>
<td headers="11" class="gt_row gt_right">--</td>
<td headers="12" class="gt_row gt_right"></td></tr>
    <tr><td headers="Variable" class="gt_row gt_left">12. Quality</td>
<td headers="Mean" class="gt_row gt_right">5.64</td>
<td headers="SD" class="gt_row gt_right">0.81</td>
<td headers="1" class="gt_row gt_right">.12**  </td>
<td headers="2" class="gt_row gt_right">-.39**  </td>
<td headers="3" class="gt_row gt_right">.23**  </td>
<td headers="4" class="gt_row gt_right">.01    </td>
<td headers="5" class="gt_row gt_right">-.13**  </td>
<td headers="6" class="gt_row gt_right">-.05*   </td>
<td headers="7" class="gt_row gt_right">-.19**  </td>
<td headers="8" class="gt_row gt_right">-.17**  </td>
<td headers="9" class="gt_row gt_right">-.06*   </td>
<td headers="10" class="gt_row gt_right">.25**  </td>
<td headers="11" class="gt_row gt_right">.48**  </td>
<td headers="12" class="gt_row gt_right">--</td></tr>
  </tbody>
  <tfoot class="gt_sourcenotes">
    <tr>
      <td class="gt_sourcenote" colspan="15"><i>Note</i>.  *<i>p</i> < .05. **<i>p</i> < .01.</td>
    </tr>
  </tfoot>
  &#10;</table>
</div>
<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-4-1.png" width="672" />
<table class="table table-bordered" style="margin-left: auto; margin-right: auto;">
<caption>
<span id="tab:unnamed-chunk-4"></span>Table 2: CTG数据
</caption>
<thead>
<tr>
<th style="text-align:right;color: white !important;background-color: #696969 !important;">
fixed.acidity
</th>
<th style="text-align:right;color: white !important;background-color: #696969 !important;">
volatile.acidity
</th>
<th style="text-align:right;color: white !important;background-color: #696969 !important;">
citric.acid
</th>
<th style="text-align:right;color: white !important;background-color: #696969 !important;">
residual.sugar
</th>
<th style="text-align:right;color: white !important;background-color: #696969 !important;">
chlorides
</th>
<th style="text-align:right;color: white !important;background-color: #696969 !important;">
free.sulfur.dioxide
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:right;">
7.4
</td>
<td style="text-align:right;">
0.70
</td>
<td style="text-align:right;">
0.00
</td>
<td style="text-align:right;">
1.9
</td>
<td style="text-align:right;">
0.076
</td>
<td style="text-align:right;">
11
</td>
</tr>
<tr>
<td style="text-align:right;">
7.8
</td>
<td style="text-align:right;">
0.88
</td>
<td style="text-align:right;">
0.00
</td>
<td style="text-align:right;">
2.6
</td>
<td style="text-align:right;">
0.098
</td>
<td style="text-align:right;">
25
</td>
</tr>
<tr>
<td style="text-align:right;">
7.8
</td>
<td style="text-align:right;">
0.76
</td>
<td style="text-align:right;">
0.04
</td>
<td style="text-align:right;">
2.3
</td>
<td style="text-align:right;">
0.092
</td>
<td style="text-align:right;">
15
</td>
</tr>
<tr>
<td style="text-align:right;">
11.2
</td>
<td style="text-align:right;">
0.28
</td>
<td style="text-align:right;">
0.56
</td>
<td style="text-align:right;">
1.9
</td>
<td style="text-align:right;">
0.075
</td>
<td style="text-align:right;">
17
</td>
</tr>
<tr>
<td style="text-align:right;">
7.4
</td>
<td style="text-align:right;">
0.70
</td>
<td style="text-align:right;">
0.00
</td>
<td style="text-align:right;">
1.9
</td>
<td style="text-align:right;">
0.076
</td>
<td style="text-align:right;">
11
</td>
</tr>
</tbody>
</table>
<table class="table table-bordered" style="margin-left: auto; margin-right: auto;">
<caption>
<span id="tab:unnamed-chunk-4"></span>Table 2: CTG数据
</caption>
<thead>
<tr>
<th style="text-align:right;color: white !important;background-color: #696969 !important;">
total.sulfur.dioxide
</th>
<th style="text-align:right;color: white !important;background-color: #696969 !important;">
density
</th>
<th style="text-align:right;color: white !important;background-color: #696969 !important;">
pH
</th>
<th style="text-align:right;color: white !important;background-color: #696969 !important;">
sulphates
</th>
<th style="text-align:right;color: white !important;background-color: #696969 !important;">
alcohol
</th>
<th style="text-align:left;color: white !important;background-color: #696969 !important;">
quality
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:right;">
34
</td>
<td style="text-align:right;">
0.9978
</td>
<td style="text-align:right;">
3.51
</td>
<td style="text-align:right;">
0.56
</td>
<td style="text-align:right;">
9.4
</td>
<td style="text-align:left;">
5
</td>
</tr>
<tr>
<td style="text-align:right;">
67
</td>
<td style="text-align:right;">
0.9968
</td>
<td style="text-align:right;">
3.20
</td>
<td style="text-align:right;">
0.68
</td>
<td style="text-align:right;">
9.8
</td>
<td style="text-align:left;">
5
</td>
</tr>
<tr>
<td style="text-align:right;">
54
</td>
<td style="text-align:right;">
0.9970
</td>
<td style="text-align:right;">
3.26
</td>
<td style="text-align:right;">
0.65
</td>
<td style="text-align:right;">
9.8
</td>
<td style="text-align:left;">
5
</td>
</tr>
<tr>
<td style="text-align:right;">
60
</td>
<td style="text-align:right;">
0.9980
</td>
<td style="text-align:right;">
3.16
</td>
<td style="text-align:right;">
0.58
</td>
<td style="text-align:right;">
9.8
</td>
<td style="text-align:left;">
6
</td>
</tr>
<tr>
<td style="text-align:right;">
34
</td>
<td style="text-align:right;">
0.9978
</td>
<td style="text-align:right;">
3.51
</td>
<td style="text-align:right;">
0.56
</td>
<td style="text-align:right;">
9.4
</td>
<td style="text-align:left;">
5
</td>
</tr>
</tbody>
</table>
<table style="width: auto;" class="table table-condensed">
<caption>
<span id="tab:unnamed-chunk-4"></span>Table 2: Data summary
</caption>
<tbody>
<tr>
<td style="text-align:left;">
Name
</td>
<td style="text-align:left;">
d
</td>
</tr>
<tr>
<td style="text-align:left;">
Number of rows
</td>
<td style="text-align:left;">
1599
</td>
</tr>
<tr>
<td style="text-align:left;">
Number of columns
</td>
<td style="text-align:left;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
</td>
<td style="text-align:left;">
</td>
</tr>
<tr>
<td style="text-align:left;">
Column type frequency:
</td>
<td style="text-align:left;">
</td>
</tr>
<tr>
<td style="text-align:left;">
factor
</td>
<td style="text-align:left;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
11
</td>
</tr>
<tr>
<td style="text-align:left;">
\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
</td>
<td style="text-align:left;">
</td>
</tr>
<tr>
<td style="text-align:left;">
Group variables
</td>
<td style="text-align:left;">
None
</td>
</tr>
</tbody>
</table>

**Variable type: factor**

<table>
<thead>
<tr>
<th style="text-align:left;">
skim_variable
</th>
<th style="text-align:right;">
n_missing
</th>
<th style="text-align:right;">
complete_rate
</th>
<th style="text-align:left;">
ordered
</th>
<th style="text-align:right;">
n_unique
</th>
<th style="text-align:left;">
top_counts
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
quality
</td>
<td style="text-align:right;">
0
</td>
<td style="text-align:right;">
1
</td>
<td style="text-align:left;">
TRUE
</td>
<td style="text-align:right;">
6
</td>
<td style="text-align:left;">
5: 681, 6: 638, 7: 199, 4: 53
</td>
</tr>
</tbody>
</table>

**Variable type: numeric**

<table>
<thead>
<tr>
<th style="text-align:left;">
skim_variable
</th>
<th style="text-align:right;">
n_missing
</th>
<th style="text-align:right;">
complete_rate
</th>
<th style="text-align:right;">
mean
</th>
<th style="text-align:right;">
sd
</th>
<th style="text-align:right;">
p0
</th>
<th style="text-align:right;">
p25
</th>
<th style="text-align:right;">
p50
</th>
<th style="text-align:right;">
p75
</th>
<th style="text-align:right;">
p100
</th>
<th style="text-align:left;">
hist
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
fixed.acidity
</td>
<td style="text-align:right;">
0
</td>
<td style="text-align:right;">
1
</td>
<td style="text-align:right;">
8.32
</td>
<td style="text-align:right;">
1.74
</td>
<td style="text-align:right;">
4.60
</td>
<td style="text-align:right;">
7.10
</td>
<td style="text-align:right;">
7.90
</td>
<td style="text-align:right;">
9.20
</td>
<td style="text-align:right;">
15.90
</td>
<td style="text-align:left;">
▂▇▂▁▁
</td>
</tr>
<tr>
<td style="text-align:left;">
volatile.acidity
</td>
<td style="text-align:right;">
0
</td>
<td style="text-align:right;">
1
</td>
<td style="text-align:right;">
0.53
</td>
<td style="text-align:right;">
0.18
</td>
<td style="text-align:right;">
0.12
</td>
<td style="text-align:right;">
0.39
</td>
<td style="text-align:right;">
0.52
</td>
<td style="text-align:right;">
0.64
</td>
<td style="text-align:right;">
1.58
</td>
<td style="text-align:left;">
▅▇▂▁▁
</td>
</tr>
<tr>
<td style="text-align:left;">
citric.acid
</td>
<td style="text-align:right;">
0
</td>
<td style="text-align:right;">
1
</td>
<td style="text-align:right;">
0.27
</td>
<td style="text-align:right;">
0.19
</td>
<td style="text-align:right;">
0.00
</td>
<td style="text-align:right;">
0.09
</td>
<td style="text-align:right;">
0.26
</td>
<td style="text-align:right;">
0.42
</td>
<td style="text-align:right;">
1.00
</td>
<td style="text-align:left;">
▇▆▅▁▁
</td>
</tr>
<tr>
<td style="text-align:left;">
residual.sugar
</td>
<td style="text-align:right;">
0
</td>
<td style="text-align:right;">
1
</td>
<td style="text-align:right;">
2.54
</td>
<td style="text-align:right;">
1.41
</td>
<td style="text-align:right;">
0.90
</td>
<td style="text-align:right;">
1.90
</td>
<td style="text-align:right;">
2.20
</td>
<td style="text-align:right;">
2.60
</td>
<td style="text-align:right;">
15.50
</td>
<td style="text-align:left;">
▇▁▁▁▁
</td>
</tr>
<tr>
<td style="text-align:left;">
chlorides
</td>
<td style="text-align:right;">
0
</td>
<td style="text-align:right;">
1
</td>
<td style="text-align:right;">
0.09
</td>
<td style="text-align:right;">
0.05
</td>
<td style="text-align:right;">
0.01
</td>
<td style="text-align:right;">
0.07
</td>
<td style="text-align:right;">
0.08
</td>
<td style="text-align:right;">
0.09
</td>
<td style="text-align:right;">
0.61
</td>
<td style="text-align:left;">
▇▁▁▁▁
</td>
</tr>
<tr>
<td style="text-align:left;">
free.sulfur.dioxide
</td>
<td style="text-align:right;">
0
</td>
<td style="text-align:right;">
1
</td>
<td style="text-align:right;">
15.87
</td>
<td style="text-align:right;">
10.46
</td>
<td style="text-align:right;">
1.00
</td>
<td style="text-align:right;">
7.00
</td>
<td style="text-align:right;">
14.00
</td>
<td style="text-align:right;">
21.00
</td>
<td style="text-align:right;">
72.00
</td>
<td style="text-align:left;">
▇▅▁▁▁
</td>
</tr>
<tr>
<td style="text-align:left;">
total.sulfur.dioxide
</td>
<td style="text-align:right;">
0
</td>
<td style="text-align:right;">
1
</td>
<td style="text-align:right;">
46.47
</td>
<td style="text-align:right;">
32.90
</td>
<td style="text-align:right;">
6.00
</td>
<td style="text-align:right;">
22.00
</td>
<td style="text-align:right;">
38.00
</td>
<td style="text-align:right;">
62.00
</td>
<td style="text-align:right;">
289.00
</td>
<td style="text-align:left;">
▇▂▁▁▁
</td>
</tr>
<tr>
<td style="text-align:left;">
density
</td>
<td style="text-align:right;">
0
</td>
<td style="text-align:right;">
1
</td>
<td style="text-align:right;">
1.00
</td>
<td style="text-align:right;">
0.00
</td>
<td style="text-align:right;">
0.99
</td>
<td style="text-align:right;">
1.00
</td>
<td style="text-align:right;">
1.00
</td>
<td style="text-align:right;">
1.00
</td>
<td style="text-align:right;">
1.00
</td>
<td style="text-align:left;">
▁▃▇▂▁
</td>
</tr>
<tr>
<td style="text-align:left;">
pH
</td>
<td style="text-align:right;">
0
</td>
<td style="text-align:right;">
1
</td>
<td style="text-align:right;">
3.31
</td>
<td style="text-align:right;">
0.15
</td>
<td style="text-align:right;">
2.74
</td>
<td style="text-align:right;">
3.21
</td>
<td style="text-align:right;">
3.31
</td>
<td style="text-align:right;">
3.40
</td>
<td style="text-align:right;">
4.01
</td>
<td style="text-align:left;">
▁▅▇▂▁
</td>
</tr>
<tr>
<td style="text-align:left;">
sulphates
</td>
<td style="text-align:right;">
0
</td>
<td style="text-align:right;">
1
</td>
<td style="text-align:right;">
0.66
</td>
<td style="text-align:right;">
0.17
</td>
<td style="text-align:right;">
0.33
</td>
<td style="text-align:right;">
0.55
</td>
<td style="text-align:right;">
0.62
</td>
<td style="text-align:right;">
0.73
</td>
<td style="text-align:right;">
2.00
</td>
<td style="text-align:left;">
▇▅▁▁▁
</td>
</tr>
<tr>
<td style="text-align:left;">
alcohol
</td>
<td style="text-align:right;">
0
</td>
<td style="text-align:right;">
1
</td>
<td style="text-align:right;">
10.42
</td>
<td style="text-align:right;">
1.07
</td>
<td style="text-align:right;">
8.40
</td>
<td style="text-align:right;">
9.50
</td>
<td style="text-align:right;">
10.20
</td>
<td style="text-align:right;">
11.10
</td>
<td style="text-align:right;">
14.90
</td>
<td style="text-align:left;">
▇▇▃▁▁
</td>
</tr>
</tbody>
</table>

# 可视化

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-5-1.png" width="672" />

# 非参数检验

## 多样本位置检验：六种质量下的红酒酒精浓度中位数是否不同？

$$
H_0:same\ vs\ H_1:not
$$

    ## 
    ## 	Kruskal-Wallis rank sum test
    ## 
    ## data:  alcohol by quality
    ## Kruskal-Wallis chi-squared = 412.38, df = 5, p-value <
    ## 0.00000000000000022

$$
H_0:same\ vs\ H_1:increasing
$$

    ## 
    ## 	Jonckheere-Terpstra test
    ## 
    ## data:  alcohol by quality
    ## JT = 602267, p-value < 0.00000000000000022
    ## alternative hypothesis: increasing

## 独立两样本比较的Wilcoxon秩和检验

将红酒分成两组,
比较质量为3，4，5与6，7，8的红酒样本的酒精浓度中位数是否有显著性
差异
$$
\\H_0:\Delta=0
$$

    ## 
    ## 	Wilcoxon rank sum test with continuity correction
    ## 
    ## data:  d1$alcohol and d2$alcohol
    ## W = 154807, p-value < 0.00000000000000022
    ## alternative hypothesis: true location shift is not equal to 0

检验结果可见两组中位数确实有显著性差异

## 相关性检验

$$
H_0:unrelated\ vs\ H_1:related
$$

### spearman

    ## 
    ## 	Spearman's rank correlation rho
    ## 
    ## data:  d$alcohol and as.numeric(d$quality)
    ## S = 355321833, p-value < 0.00000000000000022
    ## alternative hypothesis: true rho is not equal to 0
    ## sample estimates:
    ##       rho 
    ## 0.4785317

### Kendall

将酒精浓度转化为有序类别变量

$$
Kendall's \ \tau_b\\\
$$

    ## 
    ## 	Kendall's rank correlation tau
    ## 
    ## data:  d$alcohol and as.numeric(d$quality)
    ## z = 19.416, p-value < 0.00000000000000022
    ## alternative hypothesis: true tau is not equal to 0
    ## sample estimates:
    ##       tau 
    ## 0.3803673

## 分布检验

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-11-1.png" width="672" />

## 红酒密度的分布是否符合正态

$$
H_0:norm\ vs\ H_1:unnorm
$$

    ## 
    ## 	Asymptotic one-sample Kolmogorov-Smirnov test
    ## 
    ## data:  x
    ## D = 0.49781, p-value < 0.00000000000000022
    ## alternative hypothesis: two-sided

接下来比较一下先前分出的两组红酒的酒精浓度分布是否不同
$$
H_0:same\  pdf\ vs\ H_1:unsame
$$

    ## 
    ## 	Asymptotic two-sample Kolmogorov-Smirnov test
    ## 
    ## data:  d1$alcohol and d2$alcohol
    ## D = 0.4103, p-value < 0.00000000000000022
    ## alternative hypothesis: two-sided

# 一元核密度估计

这里使用插入法计算宽窗

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-14-1.png" width="672" />

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-14-2.png" width="672" />

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-14-3.png" width="672" />

## 多元核密度估计

对酒精浓度与密度做二元核密度估计

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-15-1.png" width="672" />

# 分类

先分好训练集与测试集，且要保证好酒与坏酒的比例与原数据集相近

## logistic回归

$$
cheap\ wine1(3,4,5)and\ good\ wine2(6,7,8)res\\
`\begin{aligned}
Y \sim & B(m, p)  \\
g(p) =& \beta_0 + \beta_1 x_1 + \dots + \beta_k x_k \\
AIC\ backward\ to\ choose\ model
\end{aligned}`
$$

    ## Start:  AIC=1514.87
    ## quality ~ fixed.acidity + volatile.acidity + citric.acid + residual.sugar + 
    ##     chlorides + free.sulfur.dioxide + total.sulfur.dioxide + 
    ##     density + pH + sulphates + alcohol
    ## 
    ##                        Df Deviance    AIC
    ## - density               1   1491.3 1513.3
    ## - pH                    1   1491.6 1513.6
    ## - residual.sugar        1   1492.0 1514.0
    ## - fixed.acidity         1   1492.2 1514.2
    ## <none>                      1490.9 1514.9
    ## - citric.acid           1   1495.7 1517.7
    ## - free.sulfur.dioxide   1   1495.9 1517.9
    ## - chlorides             1   1497.5 1519.5
    ## - total.sulfur.dioxide  1   1520.2 1542.2
    ## - sulphates             1   1530.2 1552.2
    ## - volatile.acidity      1   1534.8 1556.8
    ## - alcohol               1   1561.4 1583.4
    ## 
    ## Step:  AIC=1513.29
    ## quality ~ fixed.acidity + volatile.acidity + citric.acid + residual.sugar + 
    ##     chlorides + free.sulfur.dioxide + total.sulfur.dioxide + 
    ##     pH + sulphates + alcohol
    ## 
    ##                        Df Deviance    AIC
    ## - residual.sugar        1   1492.0 1512.0
    ## - fixed.acidity         1   1492.3 1512.3
    ## <none>                      1491.3 1513.3
    ## - pH                    1   1493.5 1513.5
    ## - citric.acid           1   1496.1 1516.1
    ## - free.sulfur.dioxide   1   1496.5 1516.5
    ## - chlorides             1   1498.3 1518.3
    ## - total.sulfur.dioxide  1   1521.4 1541.4
    ## - sulphates             1   1531.1 1551.1
    ## - volatile.acidity      1   1536.9 1556.9
    ## - alcohol               1   1660.9 1680.9
    ## 
    ## Step:  AIC=1511.97
    ## quality ~ fixed.acidity + volatile.acidity + citric.acid + chlorides + 
    ##     free.sulfur.dioxide + total.sulfur.dioxide + pH + sulphates + 
    ##     alcohol
    ## 
    ##                        Df Deviance    AIC
    ## - fixed.acidity         1   1493.1 1511.1
    ## <none>                      1492.0 1512.0
    ## - pH                    1   1494.2 1512.2
    ## - citric.acid           1   1496.5 1514.5
    ## - free.sulfur.dioxide   1   1497.5 1515.5
    ## - chlorides             1   1498.8 1516.8
    ## - total.sulfur.dioxide  1   1521.4 1539.4
    ## - sulphates             1   1531.2 1549.2
    ## - volatile.acidity      1   1537.1 1555.1
    ## - alcohol               1   1664.5 1682.5
    ## 
    ## Step:  AIC=1511.08
    ## quality ~ volatile.acidity + citric.acid + chlorides + free.sulfur.dioxide + 
    ##     total.sulfur.dioxide + pH + sulphates + alcohol
    ## 
    ##                        Df Deviance    AIC
    ## <none>                      1493.1 1511.1
    ## - citric.acid           1   1496.6 1512.6
    ## - free.sulfur.dioxide   1   1499.0 1515.0
    ## - pH                    1   1499.6 1515.6
    ## - chlorides             1   1502.6 1518.6
    ## - total.sulfur.dioxide  1   1528.5 1544.5
    ## - sulphates             1   1533.1 1549.1
    ## - volatile.acidity      1   1537.8 1553.8
    ## - alcohol               1   1664.7 1680.7

    ## 
    ## Call:
    ## glm(formula = quality ~ volatile.acidity + citric.acid + chlorides + 
    ##     free.sulfur.dioxide + total.sulfur.dioxide + pH + sulphates + 
    ##     alcohol, family = binomial, data = d_train, na.action = na.pass)
    ## 
    ## Coefficients:
    ##                       Estimate Std. Error z value             Pr(>|z|)    
    ## (Intercept)          -4.208576   1.765048  -2.384              0.01711 *  
    ## volatile.acidity     -3.065637   0.479500  -6.393       0.000000000162 ***
    ## citric.acid          -0.900490   0.482443  -1.867              0.06197 .  
    ## chlorides            -4.661593   1.551417  -3.005              0.00266 ** 
    ## free.sulfur.dioxide   0.021249   0.008701   2.442              0.01460 *  
    ## total.sulfur.dioxide -0.016536   0.002863  -5.776       0.000000007640 ***
    ## pH                   -1.303377   0.510496  -2.553              0.01068 *  
    ## sulphates             2.756569   0.462890   5.955       0.000000002599 ***
    ## alcohol               0.925309   0.078313  11.815 < 0.0000000000000002 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## (Dispersion parameter for binomial family taken to be 1)
    ## 
    ##     Null deviance: 1986.5  on 1437  degrees of freedom
    ## Residual deviance: 1493.1  on 1429  degrees of freedom
    ## AIC: 1511.1
    ## 
    ## Number of Fisher Scoring iterations: 4

模型预测：

    ## Confusion Matrix and Statistics
    ## 
    ##     truth
    ## pred  0  1
    ##    0 61 22
    ##    1 14 64
    ##                                           
    ##                Accuracy : 0.7764          
    ##                  95% CI : (0.7041, 0.8382)
    ##     No Information Rate : 0.5342          
    ##     P-Value [Acc > NIR] : 0.0000000001658 
    ##                                           
    ##                   Kappa : 0.5537          
    ##                                           
    ##  Mcnemar's Test P-Value : 0.2433          
    ##                                           
    ##             Sensitivity : 0.8133          
    ##             Specificity : 0.7442          
    ##          Pos Pred Value : 0.7349          
    ##          Neg Pred Value : 0.8205          
    ##              Prevalence : 0.4658          
    ##          Detection Rate : 0.3789          
    ##    Detection Prevalence : 0.5155          
    ##       Balanced Accuracy : 0.7788          
    ##                                           
    ##        'Positive' Class : 0               
    ## 

## KNN

    ## k-Nearest Neighbors 
    ## 
    ## 1438 samples
    ##   11 predictor
    ##    2 classes: '0', '1' 
    ## 
    ## Pre-processing: centered (11), scaled (11) 
    ## Resampling: Cross-Validated (10 fold) 
    ## Summary of sample sizes: 1294, 1294, 1294, 1294, 1294, 1294, ... 
    ## Resampling results across tuning parameters:
    ## 
    ##   k   Accuracy   Kappa    
    ##    5  0.7378399  0.4706605
    ##    7  0.7295066  0.4538168
    ##    9  0.7274524  0.4499167
    ##   11  0.7308955  0.4574831
    ##   13  0.7322650  0.4599812
    ## 
    ## Accuracy was used to select the optimal model using the largest value.
    ## The final value used for the model was k = 5.

查看训练好的模型，可知模型的准确率都超过了70%，且最优模型的k值13。

    ## Confusion Matrix and Statistics
    ## 
    ##     truth
    ## pred  0  1
    ##    0 47 19
    ##    1 28 67
    ##                                          
    ##                Accuracy : 0.7081         
    ##                  95% CI : (0.6313, 0.777)
    ##     No Information Rate : 0.5342         
    ##     P-Value [Acc > NIR] : 0.000004892    
    ##                                          
    ##                   Kappa : 0.4089         
    ##                                          
    ##  Mcnemar's Test P-Value : 0.2432         
    ##                                          
    ##             Sensitivity : 0.6267         
    ##             Specificity : 0.7791         
    ##          Pos Pred Value : 0.7121         
    ##          Neg Pred Value : 0.7053         
    ##              Prevalence : 0.4658         
    ##          Detection Rate : 0.2919         
    ##    Detection Prevalence : 0.4099         
    ##       Balanced Accuracy : 0.7029         
    ##                                          
    ##        'Positive' Class : 0              
    ## 

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-21-1.png" width="672" />

# 回归

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-22-1.png" width="672" />

## 样条光滑

\$\$

Y = \_{j=1}^p f_j(x_j) +

$$
$$
`\begin{align}   \min_{f(\cdot)}   \left\{   \sum_i [y_i - f(x_i)]^2 + \lambda \int [f''(x)]^2 \,dx   \right\} \end{align}`

\$\$

对质量7的红酒酒精浓度与酒密度进行样条光滑回归

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-23-1.png" width="672" />

## Generalized Additive Model (GAM)线性可加模型

将density作为因变量，自变量为fixed.acidity, citric.acid, residual.sugar与alcohol

    ## Loading required package: nlme

    ## 
    ## Attaching package: 'nlme'

    ## The following object is masked from 'package:dplyr':
    ## 
    ##     collapse

    ## This is mgcv 1.9-0. For overview type 'help("mgcv-package")'.

    ## 
    ## Family: gaussian 
    ## Link function: identity 
    ## 
    ## Formula:
    ## log(density) ~ s(fixed.acidity) + s(citric.acid) + s(residual.sugar) + 
    ##     s(alcohol)
    ## 
    ## Parametric coefficients:
    ##                Estimate  Std. Error t value            Pr(>|t|)    
    ## (Intercept) -0.00326042  0.00002145    -152 <0.0000000000000002 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Approximate significance of smooth terms:
    ##                     edf Ref.df      F              p-value    
    ## s(fixed.acidity)  7.411  8.295 141.62 < 0.0000000000000002 ***
    ## s(citric.acid)    4.002  5.003   3.56              0.00328 ** 
    ## s(residual.sugar) 8.618  8.950 110.70 < 0.0000000000000002 ***
    ## s(alcohol)        5.868  7.013 227.99 < 0.0000000000000002 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## R-sq.(adj) =  0.795   Deviance explained = 79.8%
    ## GCV = 7.4852e-07  Scale est. = 7.3593e-07  n = 1599

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-25-1.png" width="672" /><img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-25-2.png" width="672" /><img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-25-3.png" width="672" /><img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-25-4.png" width="672" />
