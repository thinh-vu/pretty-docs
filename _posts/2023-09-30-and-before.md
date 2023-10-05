---
title: Lịch sử thay đổi của vnstock trước 1/10/2023
---

## Cập nhật ngày 22/8/2023
- Cập nhật tệp dữ liệu **listing_companies** lên phiên bản mới nhất.
- Cập nhật hàm **financial flow**
  - Thêm tham số **get_all** để lấy tất cả dữ liệu có sẵn hoặc chỉ dữ liệu mới nhất (5 năm hoặc 10 quý).
- Cập nhật Demo Notebook để minh họa các thay đổi mới nhất.

## Cập nhật ngày 24/7/2023
- Bắt đầu triển khai chức năng truy xuất dữ liệu chứng khoán phái sinh.
- Kết hợp một chức năng sàng lọc cổ phiếu từ TCBS vào thư viện.
- Cải thiện hàm stock_historical_data với các cập nhật sau:
  - Khi độ khung thời gian (resolution) được đặt thành **1D**, cột thời gian sẽ hiển thị theo định dạng ngày **YYYY-mm-dd**.
  - Thêm một giá trị mới **derivative** cho tham số **type**, cho phép truy xuất dữ liệu phái sinh.
- Các tham chiếu hàm trong tệp README đã được cấu trúc theo các tình huống sử dụng thực tế, như Phân tích Kỹ thuật, Phân tích Cơ bản, Sàng lọc Cổ phiếu, vv. Điều này giúp cho tài liệu thân thiện và có tổ chức hơn với người dùng. Phiên bản tiếng Anh của tệp README cũng đã được cập nhật để phù hợp với phiên bản tiếng Việt.

## Updated 2023-07-22
- Added a new example code to the existing [demo notebook](https://github.com/thinh-vu/vnstock/blob/beta/demo/gen2_vnstock_demo_index_all_functions_testing_2023.ipynb) that demonstrates how to export data from Google Colab to Google Sheets.

## Updated 2023-07-14
- Released version 0.17 on Pypi
- The **beta** branch has been promoted to become the default branch, while the **main** branch will now serve as the stable version repository.
- The changes made in the **beta** branch will be merged into the **main** branch and released on PyPI on a monthly basis, starting from now onwards
- The README.md file has been updated to synchronize the English and Vietnamese versions.
- The database file listing_companies_enhanced-2023.csv in the data folder of this repository has been updated for the listing_companies function.
- A new function, price_depth, has been introduced to retrieve trading prices and volume for a list of stocks. This function can be used in conjunction with the price_board function.

## Update 2023-07-13
- Classified vnstock functions in the demo Jupyter Notebook based on 5 main pillars:
  1. Market Watch
  2. Fundamental Analysis
  3. Technical Analysis
  4. Stock Pick
  5. Trading Center
- Revised function demos to include recently updated functions.
- Restore the unit price of stock_historical_data from 1000 VND to VND by multiplying it by 1000.
- The **price_board** function has been updated.
- Implemented additional functions in the **utils.py** module to extract date values in the format of YYYY-mm-dd.

## Updated 2023-07-05
- The README.md file has been revised (applied to the Vietnamese language first).
- Functions related to SSI data source that were unavailable have been removed.
- The **financial_ratio** function has been enhanced with the following updates:
  - The resulting DataFrame now has a transposed structure, with the year/quarter serving as the index, facilitating usability.
  - The **is_all** parameter has been made optional.
- The **industry_analysis** and stock_ls_analysis functions have been improved:
  - The resulting DataFrame now has a transposed structure, with the stock ticker names as column headers, making it more user-friendly.
  - An additional **lang** parameter has been introduced, allowing the display of DataFrame columns in Vietnamese/English labels.

## Updated 2023-06-29
- Updated the stock_intraday_data function to elaborate more insights the data returned by the function and make it usable.
- Updated the stock_historical_data to support getting indices historical data.

## Updated 2023-06-22
- Referred to as version 0.15 (coming soon on Pypi)
- Introduce a new feature to the stock_historical_data function, enabling retrieval of data with multiple time resolutions. The corresponding API endpoint supporting this function has been upgraded.
  - Include a resolution parameter to allow users to obtain price data at intervals of 1 minute, 15 minutes, 30 minutes, 1 hour, or 1 day.
  - Modify the column name in the returned dataframe from tradingDate to time.
- Clearly mark functions that are not available for SSI API endpoints.
- The **mode='live'** option in the function listing_companies() has been removed. The function will now only read the company listing from a csv file on this github repo.
- Update the repo folder tree, added data folder data files, demo folder to store demo files.

## Updated 2023-06-07
Assist in providing a Vietnamese translation for the README.md file, which will be beneficial for local users.

## Updated 2023-05-20
> The **main** branch is dedicated to major updates only, while the **beta** branch is used for minor updates. Starting from now, the PyPI package will reflect the contents of the **main** branch.

- The listing_companies() function can now read the company listing from either a csv file on this github repo or a live API request.
- The stock_intraday_data () function has a new limit of 100 for the page_size parameter imposed by the TCBS.