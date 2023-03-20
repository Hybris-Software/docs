---
sidebar_position: 6
---

# useTable

## Props

### General Properties

| **Prop**                    | **Type**    | **Default**          | **Description**                                                        |
| --------------------------- | ----------- | -------------------- | ---------------------------------------------------------------------- |
| **pageSizes**               | Array       | [5, 10, 25, 50, 100] | Array of numbers that will be used as options for the page size select |
| **columns**                 | Array       | -                    | Array of objects that will be used as columns for the table            |
| **headerHeight**            | Number      | 50                   | Height of the header                                                   |
| **rowHeight**               | Number      | 65                   | Height of the rows                                                     |
| **height**                  | Number      |                      | Height of the table                                                    |
| **styles**                  | Object      |                      | Object with custom styles                                              |
| **endPoint**                | String      |                      | Endpoint to fetch the data                                             |
| **emptyDataMessage**        | String      | No data available    | Message to show when there is no data                                  |
| **extraFilters**            | Object      | {}                   | Object with extra filters to add to the query                          |
| **defaultPageSize**         | Number      | 5                    | Default page size                                                      |
| **enablePageSizeSelect**    | Boolean     | true                 | Enable page size select                                                |
| **dragWithMouse**           | Boolean     | true                 | Enable drag with mouse                                                 |
| **enableSearch**            | Boolean     | true                 | Enable search                                                          |
| **enableSearchFieldSelect** | Boolean     | true                 | Enable search field select                                             |
| **defaultSearchField**      | String      | " "                  | Default search field                                                   |
| **enableSelectableRows**    | Boolean     | true                 | Enable selectable rows                                                 |
| **enableAllowedActions**    | Boolean     | false                | Enable allowed actions                                                 |
| **allowedActions**          | Array       |                      | Array of objects with the allowed actions                              |
| **loader**                  | JSX.Element | `<Loader /> `        | loader                                                                 |

### Classes Properties

| **Prop**                          | **Type** | **Default**                | **Description**                            |
| --------------------------------- | -------- | -------------------------- | ------------------------------------------ |
| **inputSearchBaseClassName**      | String   | Style.inputSearchBaseClass | Base class name for the search input       |
| **selectabledRowsClassName**      | String   |                            | Class name for the selectable rows         |
| **searchBarClassName**            | String   |                            | Class name for the search bar              |
| **toPageInputClassName**          | String   |                            | Class name for the to page input           |
| **toPageInputBaseClassName**      | String   |                            | Base class name for the to page input      |
| **paginationButtonClassName**     | String   |                            | Class name for the pagination buttons      |
| **paginationButtonBaseClassName** | String   |                            | Base class name for the pagination buttons |
| **paginationClassName**           | String   |                            |                                            |
| **checkboxClassName**             | String   | Style.labelClass           |                                            |
| **sortingClassName**              | String   | Style.sortingClass         |                                            |
| **tooltipClassName**              | String   | Style.tooltip              |                                            |

### Icons Properties

| **Prop**                     | **Type**    | **Default**         | **Description** |
| ---------------------------- | ----------- | ------------------- | --------------- |
| **settingsIcon**             | JSX.Element | `<ImWrench />`      |                 |
| **copyToClipboardIcon**      | JSX.Element | `<AiOutlineCopy />` |                 |
| **sortingUpIcon**            | -           |                     |                 |
| **sortingDownIcon**          | -           |                     |                 |
| **activeSortIconClassName**  | String      |                     |                 |
| **disableSortIconClassName** | String      |                     |                 |

### Functions

| **Prop**                | **Type** | **Default** | **Description** |
| ----------------------- | -------- | ----------- | --------------- |
| **onSuccess**           | function | () => {}    |                 |
| **onUnauthorized**      | function | () => {}    |                 |
| **onError**             | function | () => {}    |                 |
| **onSearch**            | function | () => {}    |                 |
| **onSearchFieldChange** | function | () => {}    |                 |
| **onPageChange**        | function | () => {}    |                 |
| **onPageSizeChange**    | function | () => {}    |                 |
| **onSelectionChange**   | function | () => {}    |                 |
| **onSortChange**        | function | () => {}    |                 |

### Texts Props

- It's an object property that contains:

| **Texts Prop**        | **Type** | **Default**         | **Description** |
| --------------------- | -------- | ------------------- | --------------- |
| **actionSelect**      | string   | "Select an action"  |                 |
| **buttonAction**      | string   | "Apply"             |                 |
| **columnsSelect**     | string   | "Select a column"   |                 |
| **placeholderSearch** | string   | "Search..."         |                 |
| **settingTitle**      | string   | "Hide columns"      |                 |
| **rowsSelected**      | string   | "row(s) selected"   |                 |
| **columnByAsc**       | string   | "Sort by ASC"       |                 |
| **columnByDesc**      | string   | "Sort by DESC"      |                 |
| **hideColumn**        | string   | "Hide this column"  |                 |
| **showColumns**       | string   | "Show all columns"  |                 |
| **pageLabel**         | string   | "Page"              |                 |
| **ofPageLabel**       | string   | "of"                |                 |
| **buttonPrevious**    | string   | "Previous"          |                 |
| **buttonNext**        | string   | "Next"              |                 |
| **copyToClipboard**   | string   | "Copy to clipboard" |                 |
| **copied**            | string   | "Copied"            |                 |

## Examples:

```jsx
import React, { useRef } from "react";

// Libraries
import Table from "@hybris-software/use-table";

// Constants
import endPoints from "~/Data/endPoints";

// Styles
import Style from "./Members.module.css";

const Members = () => {
  // Variables
  const ref = useRef(null);
  const allowedActions = [
    {
      label: "Accept",
      value: "accept",
      action: () => {
        console.log("Accept");
      },
    },
    {
      label: "Reject",
      value: "reject",
      action: () => {
        console.log("Reject");
      },
    },
  ];

  const columns = [
    {
      Header: "#",
      field: "id",
      searchable: false,
      sortable: true,
      orderField: "id",
      accessor: (row) => {
        return row.id;
      },
    },
    {
      Header: "MEMBER NAME",
      field: "memberName",
      searchable: false,
      orderField: "member_name",
      sortable: false,
      accessor: (row) => {
        return `${row.firstName} ${row.lastName}`;
      },
    },
    {
      Header: "USERNAME",
      field: "userName",
      searchable: false,
      orderField: "user_name",
      sortable: false,
      accessor: (row) => {
        return row.username;
      },
    },
    {
      Header: "DATE JOINED",
      field: "dateJoined",
      searchable: false,
      orderField: "date_joined",
      sortable: true,
      accessor: (row) => {
        return formatDate(row.dateJoined);
      },
    },
  ];

  // Functions
  function formatDate(dateString) {
    const date = new Date(dateString);
    const year = date.getFullYear();
    const month = String(date.getMonth() + 1).padStart(2, "0");
    const day = String(date.getDate()).padStart(2, "0");
    const hours = String(date.getHours()).padStart(2, "0");
    const minutes = String(date.getMinutes()).padStart(2, "0");
    const seconds = String(date.getSeconds()).padStart(2, "0");
    return `${year}-${month}-${day} ${hours}:${minutes}:${seconds}`;
  }

  return (
    <section>
      <div className={Style.heading}>
        <h2>Members</h2>
      </div>
      <Table
        ref={ref}
        allowedActions={allowedActions}
        enableAllowedActions={false}
        columns={columns}
        endPoint={endPoints.referral.REFERRAL_LIST}
        enableSearch={false}
        enableSearchFieldSelect={false}
        enableSelectableRows={false}
        toPageInputBaseClassName={Style.toPageInput}
        onSortChange={(sort) => {}}
      />
    </section>
  );
};

export default Members;
```
