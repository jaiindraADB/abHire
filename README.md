import React from 'react';

const ProfileDetailsCard = () => {
  return (
    <div className="card bg-white dark:bg-white/[0.03]" style={{ width: '40%' }}>
      <div className="flex flex-col gap-6 lg:flex-row lg:items-start lg:justify-between">
        <div>
          <h4 className="card-title">Profile Details</h4>
          <div className="grid grid-cols-1 gap-4 lg:grid-cols-2 lg:gap-7 2xl:gap-x-32">
            <div>
              <p className="subheader">First Name</p>
              <p className="content">Harmeet</p>
            </div>
            <div>
              <p className="subheader">Last Name</p>
              <p className="content">Arora</p>
            </div>
            <div>
              <p className="subheader">Email</p>
              <p className="content">harmeeta2@gmail.com</p>
            </div>
            <div>
              <p className="subheader">Phone</p>
              <p className="content">7972195259</p>
            </div>
            <div>
              <p className="subheader">Date of Birth</p>
              <p className="content">2025-08-02</p>
            </div>
            <div>
              <p className="subheader">Total Experience in Months</p>
              <p className="content">111</p>
            </div>
            <div>
              <p className="subheader">Notice Period</p>
              <p className="content">null</p>
            </div>
            <div>
              <p className="subheader">Expected Joining Date</p>
              <p className="content">null</p>
            </div>
            <div>
              <p className="subheader">CV Summary</p>
              <p className="content">
                Currently working as a Content Writer with Astral Informatics Limited since Feb 2022. 
                Expertise in management and development of content for various websites. Passionate about 
                learning new techniques and concepts.
              </p>
            </div>
            <div>
              <p className="subheader">Current Salary</p>
              <p className="content">Current salary</p>
            </div>
            <div>
              <p className="subheader">Expected Salary</p>
              <p className="content">Expected salary</p>
            </div>
            <div>
              <p className="subheader">Gender</p>
              <p className="content">Female</p>
            </div>
            <div>
              <p className="subheader">City</p>
              <p className="content">city</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  );
};

export default ProfileDetailsCard;
