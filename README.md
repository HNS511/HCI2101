import React, { useState } from 'react';
import { ShieldCheck, UserCheck, Clock, Lock, Info, CheckCircle2, XCircle } from 'lucide-react';

const App = () => {
  const [status, setStatus] = useState('pending'); // pending, agreed, declined

  const handleAgree = () => setStatus('agreed');
  const handleDecline = () => setStatus('declined');

  if (status === 'agreed') {
    return (
      <div className="min-h-screen bg-gray-50 flex items-center justify-center p-4">
        <div className="max-w-md w-full bg-white rounded-2xl shadow-xl p-8 text-center border-t-4 border-teal-600">
          <CheckCircle2 className="w-16 h-16 text-teal-600 mx-auto mb-4" />
          <h2 className="text-2xl font-bold text-gray-800 mb-2">شكراً لموافقتك!</h2>
          <p className="text-gray-600 mb-6">تم تسجيل موافقتك بنجاح. يمكنك الآن الانتقال إلى الاستبيان.</p>
          <button className="w-full bg-teal-600 hover:bg-teal-700 text-white font-bold py-3 rounded-xl transition duration-200">
            الانتقال للاستبيان
          </button>
        </div>
      </div>
    );
  }

  if (status === 'declined') {
    return (
      <div className="min-h-screen bg-gray-50 flex items-center justify-center p-4">
        <div className="max-w-md w-full bg-white rounded-2xl shadow-xl p-8 text-center border-t-4 border-red-500">
          <XCircle className="w-16 h-16 text-red-500 mx-auto mb-4" />
          <h2 className="text-2xl font-bold text-gray-800 mb-2">شكراً لوقتك</h2>
          <p className="text-gray-600 mb-6">لقد اخترت عدم المشاركة. نحن نحترم قرارك ونتمنى لك يوماً سعيداً.</p>
          <button 
            onClick={() => setStatus('pending')}
            className="text-teal-600 font-medium hover:underline"
          >
            العودة لمراجعة الشروط
          </button>
        </div>
      </div>
    );
  }

  return (
    <div className="min-h-screen bg-slate-100 py-12 px-4 sm:px-6 lg:px-8 font-sans" dir="rtl">
      <div className="max-w-3xl mx-auto bg-white rounded-3xl shadow-2xl overflow-hidden">
        
        {/* Header Section */}
        <div className="bg-[#006666] p-8 text-white text-center">
          <div className="flex justify-center mb-4">
            <div className="bg-white/20 p-3 rounded-full">
              <ShieldCheck className="w-10 h-10 text-white" />
            </div>
          </div>
          <h1 className="text-2xl md:text-3xl font-bold">نموذج الموافقة الإلكتروني المستنير</h1>
          <p className="mt-2 text-teal-100 opacity-90">جامعة أم القرى | كلية الحاسب الآلي | المجموعة H</p>
        </div>

        {/* Content Body */}
        <div className="p-8">
          <div className="mb-8 border-b border-gray-100 pb-6 text-right">
            <h2 className="text-xl font-bold text-gray-800 mb-2">عنوان البحث:</h2>
            <p className="text-lg text-teal-800 font-medium italic" dir="ltr">
              Usability Evaluation of Biometric Authentication Systems
            </p>
            <div className="mt-4 flex flex-wrap gap-4 text-sm text-gray-600">
              <span className="bg-teal-50 px-3 py-1 rounded-full border border-teal-100">المقرر: HCI</span>
              <span className="bg-teal-50 px-3 py-1 rounded-full border border-teal-100">القائد: حازم العتيبي</span>
            </div>
          </div>

          <div className="space-y-6">
            <section className="flex gap-4">
              <div className="flex-shrink-0">
                <div className="bg-blue-50 p-2 rounded-lg"><Info className="text-blue-600 w-6 h-6" /></div>
              </div>
              <div className="text-right w-full">
                <h3 className="font-bold text-gray-800 mb-1">الغرض من الدراسة</h3>
                <p className="text-gray-600 leading-relaxed text-sm">
                  نهدف لتقييم سهولة استخدام تقنيات مثل بصمة الإصبع والتعرف على الوجه لفهم كيفية تصميم أنظمة أكثر فعالية للمستخدمين.
                </p>
              </div>
            </section>

            <section className="flex gap-4">
              <div className="flex-shrink-0">
                <div className="bg-orange-50 p-2 rounded-lg"><Clock className="text-orange-600 w-6 h-6" /></div>
              </div>
              <div className="text-right w-full">
                <h3 className="font-bold text-gray-800 mb-1">الوقت المتوقع</h3>
                <p className="text-gray-600 leading-relaxed text-sm">
                  لن تستغرق المشاركة أكثر من 5 إلى 10 دقائق من وقتك الثمين.
                </p>
              </div>
            </section>

            <section className="flex gap-4">
              <div className="flex-shrink-0">
                <div className="bg-green-50 p-2 rounded-lg"><Lock className="text-green-600 w-6 h-6" /></div>
              </div>
              <div className="text-right w-full">
                <h3 className="font-bold text-gray-800 mb-1">السرية التامة</h3>
                <p className="text-gray-600 leading-relaxed text-sm">
                  مشاركتك مجهولة الهوية تماماً. لن نقوم بطلب اسمك أو بريدك الإلكتروني، وتُستخدم البيانات للأغراض الأكاديمية فقط.
                </p>
              </div>
            </section>

            <section className="flex gap-4">
              <div className="flex-shrink-0">
                <div className="bg-purple-50 p-2 rounded-lg"><UserCheck className="text-purple-600 w-6 h-6" /></div>
              </div>
              <div className="text-right w-full">
                <h3 className="font-bold text-gray-800 mb-1">المشاركة التطوعية</h3>
                <p className="text-gray-600 leading-relaxed text-sm">
                  لك كامل الحرية في المشاركة أو الانسحاب في أي وقت دون أي تبعات.
                </p>
              </div>
            </section>
          </div>

          {/* Action Buttons */}
          <div className="mt-12 space-y-4">
            <p className="text-center text-xs text-gray-400 mb-4 italic">
              بالنقر على "أوافق"، فإنك تؤكد أنك فهمت المعلومات أعلاه وتوافق على المشاركة طواعية.
            </p>
            <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
              <button 
                onClick={handleAgree}
                className="bg-teal-600 hover:bg-teal-700 text-white font-bold py-4 rounded-2xl shadow-lg transition-all transform hover:-translate-y-1 active:scale-95 text-lg"
              >
                أوافق (Agree)
              </button>
              <button 
                onClick={handleDecline}
                className="bg-white border-2 border-gray-200 hover:border-red-300 hover:bg-red-50 text-gray-500 hover:text-red-600 font-bold py-4 rounded-2xl transition-all text-lg"
              >
                لا أوافق (Disagree)
              </button>
            </div>
          </div>
        </div>
        
        {/* Footer */}
        <div className="bg-gray-50 p-4 text-center border-t border-gray-100">
          <p className="text-xs text-gray-400">© 2024 فريق بحث HCI - المجموعة H - جامعة أم القرى</p>
        </div>
      </div>
    </div>
  );
};

export default App;
