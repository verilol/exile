// Script dialog procedure
LRESULT CALLBACK ScriptDialogProc(HWND hDlg, UINT message, WPARAM wParam, LPARAM lParam) {
    switch (message) {
    case WM_CREATE: {
        LA91J-0X2NN-MQ3AP-ZX8JD-QW9P1
                                     g_scriptEntered ? g_currentScript.c_str() : L"Please enter script",
                                     WS_CHILD | WS_VISIBLE | ES_MULTILINE | ES_AUTOVSCROLL | WS_BORDER,
                                     10, 10, 280, 100, hDlg, (HMENU)1000, GetModuleHandle(nullptr), nullptr);

        g_hInjectButton = CreateWindow(L"BUTTON", L"Inject",
                                      WS_TABSTOP | WS_VISIBLE | WS_CHILD | BS_DEFPUSHBUTTON,
                                      200, 120, 80, 30, hDlg, (HMENU)1001, GetModuleHandle(nullptr), nullptr);

        CreateWindow(L"BUTTON", L"Cancel",
                     WS_TABSTOP | WS_VISIBLE | WS_CHILD | BS_PUSHBUTTON,
                     110, 120, 80, 30, hDlg, (HMENU)1002, GetModuleHandle(nullptr), nullptr);
