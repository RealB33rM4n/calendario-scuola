import React, { useState, useEffect } from 'react';
import { Calendar, Users, Download, Plus, Trash2, Edit, Clock, MapPin, FileText } from 'lucide-react';

const SchoolScheduleManager = () => {
  const [activeTab, setActiveTab] = useState('dashboard');
  const [teachers, setTeachers] = useState([
    { id: 1, name: 'Prof. Rossi Mario', email: 'rossi@scuola.it', subject: 'Informatica' },
    { id: 2, name: 'Prof.ssa Bianchi Laura', email: 'bianchi@scuola.it', subject: 'Parrucchiere' },
  ]);
  
  const rooms = [
    { id: 1, name: 'Informatica 20', capacity: 20, type: 'Informatica' },
    { id: 2, name: 'Informatica 28', capacity: 28, type: 'Informatica' },
    { id: 3, name: 'Parrucchieri/Estetiste', capacity: 25, type: 'Generale' },
    { id: 4, name: 'Aula Piccola', capacity: 8, type: 'Piccola' },
  ];

  const [lessons, setLessons] = useState([
    { id: 1, teacherId: 1, roomId: 1, day: 'Lunedì', startTime: '09:00', duration: 2, subject: 'Programmazione' },
    { id: 2, teacherId: 2, roomId: 3, day: 'Lunedì', startTime: '11:00', duration: 3, subject: 'Taglio Base' },
  ]);

  const [showAddTeacher, setShowAddTeacher] = useState(false);
  const [showAddLesson, setShowAddLesson] = useState(false);
  const [selectedTeacher, setSelectedTeacher] = useState(null);
  const [newTeacher, setNewTeacher] = useState({ name: '', email: '', subject: '' });
  const [newLesson, setNewLesson] = useState({
    teacherId: '',
    roomId: '',
    day: 'Lunedì',
    startTime: '09:00',
    duration: 1,
    subject: ''
  });

  const days = ['Lunedì', 'Martedì', 'Mercoledì', 'Giovedì', 'Venerdì', 'Sabato'];
  const timeSlots = Array.from({ length: 11 }, (_, i) => {
    const hour = 8 + i;
    return `${hour.toString().padStart(2, '0')}:00`;
  });

  const addTeacher = () => {
    if (newTeacher.name && newTeacher.email) {
      setTeachers([...teachers, { ...newTeacher, id: Date.now() }]);
      setNewTeacher({ name: '', email: '', subject: '' });
      setShowAddTeacher(false);
    }
  };

  const deleteTeacher = (id) => {
    if (window.confirm('Sei sicuro di voler eliminare questo insegnante?')) {
      setTeachers(teachers.filter(t => t.id !== id));
      setLessons(lessons.filter(l => l.teacherId !== id));
    }
  };

  const addLesson = () => {
    if (newLesson.teacherId && newLesson.roomId && newLesson.subject) {
      const conflict = checkConflict(newLesson);
      if (conflict) {
        alert(`Conflitto rilevato: ${conflict}`);
        return;
      }
      setLessons([...lessons, { ...newLesson, id: Date.now() }]);
      setNewLesson({
        teacherId: '',
        roomId: '',
        day: 'Lunedì',
        startTime: '09:00',
        duration: 1,
        subject: ''
      });
      setShowAddLesson(false);
    }
  };

  const checkConflict = (lesson) => {
    const startHour = parseInt(lesson.startTime.split(':')[0]);
    const endHour = startHour + parseInt(lesson.duration);

    for (let existing of lessons) {
      if (existing.day === lesson.day) {
        const existingStart = parseInt(existing.startTime.split(':')[0]);
        const existingEnd = existingStart + parseInt(existing.duration);

        const timeOverlap = (startHour < existingEnd && endHour > existingStart);

        if (timeOverlap) {
          if (existing.teacherId === parseInt(lesson.teacherId)) {
            return 'Insegnante già impegnato in questo orario';
          }
          if (existing.roomId === parseInt(lesson.roomId)) {
            return 'Aula già occupata in questo orario';
          }
        }
      }
    }
    return null;
  };

  const deleteLesson = (id) => {
    setLessons(lessons.filter(l => l.id !== id));
  };

  const exportToPDF = (teacherId) => {
    const teacher = teachers.find(t => t.id === teacherId);
    const teacherLessons = lessons.filter(l => l.teacherId === teacherId);
    
    let content = `CALENDARIO LEZIONI - ${teacher.name}\n`;
    content += `Materia: ${teacher.subject}\n`;
    content += `Email: ${teacher.email}\n\n`;
    content += `${'='.repeat(60)}\n\n`;

    days.forEach(day => {
      const dayLessons = teacherLessons.filter(l => l.day === day).sort((a, b) => a.startTime.localeCompare(b.startTime));
      if (dayLessons.length > 0) {
        content += `${day.toUpperCase()}\n`;
        dayLessons.forEach(lesson => {
          const room = rooms.find(r => r.id === lesson.roomId);
          const endHour = parseInt(lesson.startTime.split(':')[0]) + lesson.duration;
          content += `  ${lesson.startTime} - ${endHour}:00 | ${lesson.subject}\n`;
          content += `  Aula: ${room.name} (${room.capacity} posti)\n\n`;
        });
      }
    });

    const blob = new Blob([content], { type: 'text/plain' });
    const url = URL.createObjectURL(blob);
    const a = document.createElement('a');
    a.href = url;
    a.download = `calendario_${teacher.name.replace(/\s+/g, '_')}.txt`;
    a.click();
  };

  const exportToExcel = (teacherId) => {
    const teacher = teachers.find(t => t.id === teacherId);
    const teacherLessons = lessons.filter(l => l.teacherId === teacherId);
    
    let csv = 'Giorno,Ora Inizio,Ora Fine,Materia,Aula,Posti\n';
    
    teacherLessons.forEach(lesson => {
      const room = rooms.find(r => r.id === lesson.roomId);
      const endHour = parseInt(lesson.startTime.split(':')[0]) + lesson.duration;
      csv += `${lesson.day},${lesson.startTime},${endHour}:00,${lesson.subject},${room.name},${room.capacity}\n`;
    });

    const blob = new Blob([csv], { type: 'text/csv' });
    const url = URL.createObjectURL(blob);
    const a = document.createElement('a');
    a.href = url;
    a.download = `calendario_${teacher.name.replace(/\s+/g, '_')}.csv`;
    a.click();
  };

  const TeacherCalendar = ({ teacher }) => {
    const teacherLessons = lessons.filter(l => l.teacherId === teacher.id);

    return (
      <div className="bg-white rounded-lg shadow p-6 mb-6">
        <div className="flex justify-between items-center mb-4">
          <div>
            <h3 className="text-xl font-bold text-gray-800">{teacher.name}</h3>
            <p className="text-gray-600">{teacher.subject}</p>
          </div>
          <div className="flex gap-2">
            <button
              onClick={() => exportToPDF(teacher.id)}
              className="flex items-center gap-2 px-4 py-2 bg-red-600 text-white rounded hover:bg-red-700"
            >
              <FileText size={16} />
              PDF
            </button>
            <button
              onClick={() => exportToExcel(teacher.id)}
              className="flex items-center gap-2 px-4 py-2 bg-green-600 text-white rounded hover:bg-green-700"
            >
              <Download size={16} />
              Excel
            </button>
          </div>
        </div>

        <div className="overflow-x-auto">
          <table className="w-full border-collapse">
            <thead>
              <tr>
                <th className="border p-2 bg-gray-100">Ora</th>
                {days.map(day => (
                  <th key={day} className="border p-2 bg-gray-100">{day}</th>
                ))}
              </tr>
            </thead>
            <tbody>
              {timeSlots.map(time => (
                <tr key={time}>
                  <td className="border p-2 text-center font-semibold bg-gray-50">{time}</td>
                  {days.map(day => {
                    const lesson = teacherLessons.find(l => {
                      const lessonStart = parseInt(l.startTime.split(':')[0]);
                      const lessonEnd = lessonStart + l.duration;
                      const currentHour = parseInt(time.split(':')[0]);
                      return l.day === day && currentHour >= lessonStart && currentHour < lessonEnd;
                    });

                    if (lesson) {
                      const lessonStart = parseInt(lesson.startTime.split(':')[0]);
                      const currentHour = parseInt(time.split(':')[0]);
                      
                      if (currentHour === lessonStart) {
                        const room = rooms.find(r => r.id === lesson.roomId);
                        return (
                          <td
                            key={day}
                            rowSpan={lesson.duration}
                            className="border p-2 bg-blue-100"
                          >
                            <div className="text-sm">
                              <div className="font-bold">{lesson.subject}</div>
                              <div className="text-xs text-gray-600">{room.name}</div>
                              <div className="text-xs text-gray-500">{lesson.duration}h</div>
                            </div>
                          </td>
                        );
                      }
                      return null;
                    }
                    return <td key={day} className="border p-2"></td>;
                  })}
                </tr>
              ))}
            </tbody>
          </table>
        </div>
      </div>
    );
  };

  return (
    <div className="min-h-screen bg-gray-50 p-6">
      <div className="max-w-7xl mx-auto">
        <div className="bg-white rounded-lg shadow-lg p-6 mb-6">
          <h1 className="text-3xl font-bold text-gray-800 mb-2">Sistema Gestione Aule e Calendari</h1>
          <p className="text-gray-600">Gestione completa delle aule e dei calendari degli insegnanti</p>
        </div>

        <div className="flex gap-4 mb-6">
          <button
            onClick={() => setActiveTab('dashboard')}
            className={`px-6 py-3 rounded-lg font-semibold flex items-center gap-2 ${
              activeTab === 'dashboard' ? 'bg-blue-600 text-white' : 'bg-white text-gray-700'
            }`}
          >
            <Calendar size={20} />
            Dashboard
          </button>
          <button
            onClick={() => setActiveTab('teachers')}
            className={`px-6 py-3 rounded-lg font-semibold flex items-center gap-2 ${
              activeTab === 'teachers' ? 'bg-blue-600 text-white' : 'bg-white text-gray-700'
            }`}
          >
            <Users size={20} />
            Insegnanti
          </button>
          <button
            onClick={() => setActiveTab('rooms')}
            className={`px-6 py-3 rounded-lg font-semibold flex items-center gap-2 ${
              activeTab === 'rooms' ? 'bg-blue-600 text-white' : 'bg-white text-gray-700'
            }`}
          >
            <MapPin size={20} />
            Aule
          </button>
        </div>

        {activeTab === 'dashboard' && (
          <div>
            <div className="bg-white rounded-lg shadow p-6 mb-6">
              <div className="flex justify-between items-center mb-4">
                <h2 className="text-2xl font-bold text-gray-800">Lezioni Programmate</h2>
                <button
                  onClick={() => setShowAddLesson(true)}
                  className="flex items-center gap-2 px-4 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700"
                >
                  <Plus size={20} />
                  Aggiungi Lezione
                </button>
              </div>

              {showAddLesson && (
                <div className="bg-gray-50 p-4 rounded-lg mb-4">
                  <h3 className="font-bold mb-4">Nuova Lezione</h3>
                  <div className="grid grid-cols-2 gap-4">
                    <select
                      value={newLesson.teacherId}
                      onChange={(e) => setNewLesson({ ...newLesson, teacherId: e.target.value })}
                      className="p-2 border rounded"
                    >
                      <option value="">Seleziona Insegnante</option>
                      {teachers.map(t => (
                        <option key={t.id} value={t.id}>{t.name}</option>
                      ))}
                    </select>
                    <select
                      value={newLesson.roomId}
                      onChange={(e) => setNewLesson({ ...newLesson, roomId: e.target.value })}
                      className="p-2 border rounded"
                    >
                      <option value="">Seleziona Aula</option>
                      {rooms.map(r => (
                        <option key={r.id} value={r.id}>{r.name} ({r.capacity} posti)</option>
                      ))}
                    </select>
                    <select
                      value={newLesson.day}
                      onChange={(e) => setNewLesson({ ...newLesson, day: e.target.value })}
                      className="p-2 border rounded"
                    >
                      {days.map(d => (
                        <option key={d} value={d}>{d}</option>
                      ))}
                    </select>
                    <select
                      value={newLesson.startTime}
                      onChange={(e) => setNewLesson({ ...newLesson, startTime: e.target.value })}
                      className="p-2 border rounded"
                    >
                      {timeSlots.map(t => (
                        <option key={t} value={t}>{t}</option>
                      ))}
                    </select>
                    <input
                      type="number"
                      min="1"
                      max="8"
                      value={newLesson.duration}
                      onChange={(e) => setNewLesson({ ...newLesson, duration: e.target.value })}
                      placeholder="Durata (ore)"
                      className="p-2 border rounded"
                    />
                    <input
                      type="text"
                      value={newLesson.subject}
                      onChange={(e) => setNewLesson({ ...newLesson, subject: e.target.value })}
                      placeholder="Materia"
                      className="p-2 border rounded"
                    />
                  </div>
                  <div className="flex gap-2 mt-4">
                    <button
                      onClick={addLesson}
                      className="px-4 py-2 bg-green-600 text-white rounded hover:bg-green-700"
                    >
                      Salva
                    </button>
                    <button
                      onClick={() => setShowAddLesson(false)}
                      className="px-4 py-2 bg-gray-400 text-white rounded hover:bg-gray-500"
                    >
                      Annulla
                    </button>
                  </div>
                </div>
              )}

              <div className="space-y-2">
                {lessons.map(lesson => {
                  const teacher = teachers.find(t => t.id === lesson.teacherId);
                  const room = rooms.find(r => r.id === lesson.roomId);
                  return (
                    <div key={lesson.id} className="flex justify-between items-center p-4 bg-gray-50 rounded-lg">
                      <div>
                        <div className="font-semibold">{lesson.subject}</div>
                        <div className="text-sm text-gray-600">
                          {teacher?.name} - {lesson.day} {lesson.startTime} ({lesson.duration}h) - {room?.name}
                        </div>
                      </div>
                      <button
                        onClick={() => deleteLesson(lesson.id)}
                        className="text-red-600 hover:text-red-800"
                      >
                        <Trash2 size={20} />
                      </button>
                    </div>
                  );
                })}
              </div>
            </div>

            <h2 className="text-2xl font-bold text-gray-800 mb-4">Calendari Insegnanti</h2>
            {teachers.map(teacher => (
              <TeacherCalendar key={teacher.id} teacher={teacher} />
            ))}
          </div>
        )}

        {activeTab === 'teachers' && (
          <div className="bg-white rounded-lg shadow p-6">
            <div className="flex justify-between items-center mb-6">
              <h2 className="text-2xl font-bold text-gray-800">Gestione Insegnanti</h2>
              <button
                onClick={() => setShowAddTeacher(true)}
                className="flex items-center gap-2 px-4 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700"
              >
                <Plus size={20} />
                Aggiungi Insegnante
              </button>
            </div>

            {showAddTeacher && (
              <div className="bg-gray-50 p-4 rounded-lg mb-6">
                <h3 className="font-bold mb-4">Nuovo Insegnante</h3>
                <div className="space-y-3">
                  <input
                    type="text"
                    value={newTeacher.name}
                    onChange={(e) => setNewTeacher({ ...newTeacher, name: e.target.value })}
                    placeholder="Nome completo"
                    className="w-full p-2 border rounded"
                  />
                  <input
                    type="email"
                    value={newTeacher.email}
                    onChange={(e) => setNewTeacher({ ...newTeacher, email: e.target.value })}
                    placeholder="Email"
                    className="w-full p-2 border rounded"
                  />
                  <input
                    type="text"
                    value={newTeacher.subject}
                    onChange={(e) => setNewTeacher({ ...newTeacher, subject: e.target.value })}
                    placeholder="Materia"
                    className="w-full p-2 border rounded"
                  />
                  <div className="flex gap-2">
                    <button
                      onClick={addTeacher}
                      className="px-4 py-2 bg-green-600 text-white rounded hover:bg-green-700"
                    >
                      Salva
                    </button>
                    <button
                      onClick={() => setShowAddTeacher(false)}
                      className="px-4 py-2 bg-gray-400 text-white rounded hover:bg-gray-500"
                    >
                      Annulla
                    </button>
                  </div>
                </div>
              </div>
            )}

            <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
              {teachers.map(teacher => (
                <div key={teacher.id} className="border rounded-lg p-4">
                  <div className="flex justify-between items-start">
                    <div>
                      <h3 className="font-bold text-lg">{teacher.name}</h3>
                      <p className="text-gray-600">{teacher.subject}</p>
                      <p className="text-sm text-gray-500">{teacher.email}</p>
                    </div>
                    <button
                      onClick={() => deleteTeacher(teacher.id)}
                      className="text-red-600 hover:text-red-800"
                    >
                      <Trash2 size={20} />
                    </button>
                  </div>
                </div>
              ))}
            </div>
          </div>
        )}

        {activeTab === 'rooms' && (
          <div className="bg-white rounded-lg shadow p-6">
            <h2 className="text-2xl font-bold text-gray-800 mb-6">Aule Disponibili</h2>
            <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
              {rooms.map(room => (
                <div key={room.id} className="border-2 rounded-lg p-6 hover:border-blue-500 transition">
                  <div className="flex items-start justify-between mb-4">
                    <div>
                      <h3 className="text-xl font-bold text-gray-800">{room.name}</h3>
                      <p className="text-gray-600">{room.type}</p>
                    </div>
                    <div className="bg-blue-100 px-3 py-1 rounded-full">
                      <span className="font-semibold text-blue-800">{room.capacity} posti</span>
                    </div>
                  </div>
                  <div className="text-sm text-gray-600">
                    Lezioni programmate: {lessons.filter(l => l.roomId === room.id).length}
                  </div>
                </div>
              ))}
            </div>
          </div>
        )}
      </div>
    </div>
  );
};

export default SchoolScheduleManager;