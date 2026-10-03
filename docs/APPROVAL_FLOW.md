# تدفق موافقات Power Platform

## السيناريو
موظف يقدّم طلب شراء/صيانة عبر Power App، ثم يمر بموافقة المدير عبر Power Automate.

## المكونات
1. **SharePoint List** أو Dataverse Table: PurchaseRequests
2. **Power App**: نموذج إدخال الطلب
3. **Power Automate Flow**: عند إنشاء عنصر → Start and wait for an approval → تحديث الحالة

## حقول مقترحة
- Title
- Amount
- Department
- RequestedBy
- Status (Pending/Approved/Rejected)
- ApproverEmail

## خطوات Flow
1. Trigger: When an item is created
2. Condition: Amount > 5000 → مدير أعلى، وإلا مدير مباشر
3. Action: Start and wait for an approval (Approve/Reject)
4. Update item Status + إرسال إشعار للطلب
